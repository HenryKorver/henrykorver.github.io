---
layout: essay
type: essay
title: "Software Engineering is more than just code"
# All dates must be YYYY-MM-DD format!
date: 2025-12-17
published: true
labels:
  - Software Engineering
  - Learning
  - TypeScript
---

When I first started my ICS 314 class, I used the terms "software development" and "software engineering" interchangeably. After completing this class, the difference is notable. In part, the difference is the toolset. Software engineers use tools like Configuration Management and Agile Project Management, while better communicating using a set of Coding Standards and the language of Design Patterns. However, the distinction goes deeper than just the tools; it is about the rigorous processes that allow teams to build complex systems reliably. In reflecting on my experience building my final project, "Rate My Tools," three specific concepts stood out as defining factors of engineering: Configuration Management, Agile Project Management, and Coding Standards.

One of the foundational pillars of our work was Configuration Management (CM). In a general sense, configuration management is the detailed recording and updating of information that describes an enterprise's hardware and software. In the context of our coding, it refers specifically to version control—tracking changes to the source code so that a team can work simultaneously without overwriting each other's contributions. While we utilized GitHub specifically for web development, the concept of CM applies to almost any digital collaboration. whether you are writing a collaborative research paper or developing a desktop game, you need a "single source of truth" and a history of changes. For "Rate My Tools," GitHub was essential. It allowed us to configure our project so that we could experiment with new features on separate branches before merging them into the main codebase. Without this engineering standard, our collaboration would have been chaotic and prone to error.

Closely related to how we managed our code was how we managed our time and tasks, specifically through Agile Project Management. Agile is an iterative approach to project management that focuses on breaking large projects into small, manageable tasks to be completed in short cycles. We specifically utilized a flavor of this called Issue Driven Project Management (IDPM), where every task corresponds to a specific "issue" or ticket. This is a skill that translates well beyond web applications; one could use IDPM to manage the construction of a house or the planning of a large event, breaking the massive goal down into trackable, bite-sized "issues." In our project, we used GitHub Projects to implement this. It enabled us to visualize our workflow, moving tasks from "Todo" to "In Progress" to "Done." It made the abstract idea of "finishing the project" concrete and actionable, ensuring we were always making forward progress.

Finally, I learned the value of Coding Standards. This refers to a set of guidelines and best practices for writing code, covering everything from indentation and spacing to variable naming conventions. The goal is to make the code look like it was written by a single person, even if a dozen people worked on it. In "Rate My Tools," we used a tool called ESLint to enforce these standards. Initially, this was a source of frustration; we had a bunch of ESLint errors popping up constantly, flagging minor formatting issues that didn't technically break the code. However, as the project progressed, we learned to accept and appreciate these specific formatting rules. We realized that these standards are not arbitrary hurdles, but rather a way to reduce cognitive load. When the code follows a standard structure, it is easier to read, debug, and maintain.

Throughout this course, I also caught glimpses of Design Patterns—reusable solutions to common problems in software design. While we didn't always strictly use design patterns to inform our development decisions directly, it was interesting to see them at play within the frameworks we used, and I now understand why they are useful for solving structural problems efficiently.

Ultimately, this class taught me that writing code is only a small part of the job. Software Engineering is about the ecosystem around that code. By utilizing configuration management to control our versions, Agile methodology to manage our workflow, and coding standards to maintain our quality, we were able to transition from simply writing a web app to engineering a sustainable software product.
