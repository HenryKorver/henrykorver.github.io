---
layout: essay
type: essay
title: "Strapped in ready to react."
date: 2025-10-09
published: true
labels:
  - Bootstrap
---

## My experience with web frameworks started and ended with React.

As in, the word react. More exactly, that it is a popular JS framework used in large web projects. Now though, I can say the same about another framework - bootstrap. At first glance I am pretty pleased. I don't love writing HTML or CSS. I don't even really see them as a programming language (even though they are technically turing complete). As such working with Bootstrap is a pleasant timesave over plain HTML & CSS. My favorite part is the icon library however, as it makes the web developement process significantly less painful.

## Why is it called Bootstrap though?

Bootstrap started as an internal tool at Twitter. Apparently it used to be called blueprint in its closed-source infancy there. This name is good and makes sense to me. Bootstrap on the other hand makes me think about compiler bootstrapping, and is less descriptive regarding its purpose.

## An Example:

To see the power of Bootstrap in action we can consider implementing an email field.

**With Bootstrap:**
```html
<div class="mb-3">
  <label for="email" class="form-label">Email address</label>
  <input type="email" class="form-control" id="email" placeholder="name@example.com">
</div>
```

Relatively simple. The only real complexity here is determing which classes to use.

**With plain HTML/CSS:**
```html
<div class="input-group">
  <label for="email">Email address</label>
  <input type="email" id="email" placeholder="name@example.com">
</div>
```

```css
.input-group {
  margin-bottom: 1rem;
}

.input-group label {
  display: block;
  margin-bottom: 0.5rem;
  font-weight: 500;
  color: #212529;
}

.input-group input {
  display: block;
  width: 100%;
  padding: 0.375rem 0.75rem;
  font-size: 1rem;
  font-weight: 400;
  line-height: 1.5;
  color: #212529;
  background-color: #fff;
  border: 1px solid #ced4da;
  border-radius: 0.375rem;
  transition: border-color 0.15s ease-in-out, box-shadow 0.15s ease-in-out;
}

.input-group input:focus {
  color: #212529;
  background-color: #fff;
  border-color: #86b7fe;
  outline: 0;
  box-shadow: 0 0 0 0.25rem rgba(13, 110, 253, 0.25);
}
```

Not having to write your CSS here, really, honestly is very nice. It also simplifies some of the complexity in understanding the "cascade" part of the css, which can trip me up at times. 


## The Pain Point(s)

Not all is beer and skittles. If you want something strange, unique or custom, it might take more brainpower to search and find the right bootsrap component to use, alter and then optimize than just using HTML and CSS. It also might make your website run slower. Another issue I see is the lifecycle. The Bootstrap team has deprecated the framework 4x in ~10 years. I don't know if this common for similar frameworks, but if not, it might be worth considering jumping ship at some point.

## My thoughts going forward

Bootstrap is great because it allows me to plug in to large ecosystem of components which already look good. It also makes the general "blueprint" process for webpage developement much cleaner and easier. It can have some minor downsides depending on how it is used, but as a tool, it feels much faster and smoother than just using CSS and HTML.