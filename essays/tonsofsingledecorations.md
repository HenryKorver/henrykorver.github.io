---
layout: essay
type: essay
title: "Tons Of Single Decorations"
# All dates must be YYYY-MM-DD format!
date: 2025-12-04
published: true
labels:
  - Software Engineering
  - Learning
  - Design Patterns
---
Over the past week or so, we have begun to talk about software design patterns in our class. After 10+ hours, I think I can answer the following question competently:

## Why bother following Design Patterns?

At first glance, Design Patterns may seem overly complicated and abstract, but their implementation need not be. In software engineering, a design pattern is a template solution to commonly occurring problems. Unlike frameworks or libraries, they are not ready-made tools, and in fact, they are more like extra vocabulary. I'm a bit torn because on one hand, memorizing 20+ common design patterns is a little dull. On the other hand, if I tell another developer, "I'm using a factory here," I would be disappointed if I had to explain to them what a factory is. 

Design patterns can be split into three groups:

- **Creational Patterns**: Deal with object creation mechanisms (e.g., Singleton, Factory).
- **Structural Patterns**: Explain how to assemble objects and classes into larger structures (e.g., Decorator, Adapter).
- **Behavioral Patterns**: Concerned with algorithms and the assignment of responsibilities between objects (e.g., Observer, Strategy).

---

## Applied Patterns in "Rate My Tools"

In building my "Rate My Tools" application using Next.js, I specifically utilized the Singleton and Decorator patterns to manage database connections and UI composition.

### 1. The Singleton Pattern

**The Problem:**

One of the most common pitfalls in serverless or hot-reloading environments (like Next.js development) is managing database connections. If you instantiate a new database client every time a file loads, you will rapidly exhaust your database's connection limit, causing the application to crash.

**The Solution:**

The Singleton Pattern ensures a class has only one instance and provides a global point of access to it.

I implemented this using Prisma. By attaching the client to the global object in a development environment, I ensure that hot-reloads recycle the existing connection rather than creating a new one.

```typescript
import { PrismaClient } from '@prisma/client';

// 1. Create a global variable to hold the instance
const globalForPrisma = global as unknown as { prisma: PrismaClient };

// 2. Check if the instance already exists; if not, create a new one.
export const prisma =
  globalForPrisma.prisma ||
  new PrismaClient({
    log: ['query'],
  });

// 3. In development, save the instance to the global object so it persists across reloads.
if (process.env.NODE_ENV !== 'production') globalForPrisma.prisma = prisma;
```

### 2. The Decorator Pattern

**The Problem:**

In a complex web application, the main content of a page often needs to be wrapped with various functional layers: authentication state, navigation bars, and global modal contexts. Repeating this setup code for every individual page violates the DRY (Don't Repeat Yourself) principle.

**The Solution:**

The Decorator Pattern allows you to attach new behaviors to objects (or components) by wrapping them. In React, we achieve this "decoration" through composition in our Layout files.

My RootLayout acts as the primary decorator. It takes the page content (children) and wraps it with Providers (Auth/Session data), Navigation (TopMenu), and Interaction layers (AuthModalHost).

```typescript
export default function RootLayout({
  children, // <--- The component being decorated (the page content)
}: Readonly<{
  children: React.ReactNode;
}>) {
  const classString = `${inter.className} wrapper`;
  return (
    <html lang="en">
      <body className={classString}>
        {/* Decorator 1: Providers injects session data into the component tree */}
        <Providers>
          {/* Decorator 2: TopMenu adds navigation UI above the content */}
          <TopMenu title={metadata.title as string} />
          
          {/* Decorator 3: AuthModalHost adds global modal capabilities */}
          <AuthModalHost />

          {/* The Core Content */}
          <main>
             {children}
          </main>
        </Providers>
      </body>
    </html>
  );
}
```

---

## Conclusion

By strictly adhering to these patterns, the application becomes significantly more robust. The Singleton prevents resource exhaustion on the backend, while the Decorator (via Layouts) ensures a consistent UI and state management structure across the frontend without code duplication.
