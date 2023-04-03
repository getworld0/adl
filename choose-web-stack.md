# Webapp will be written in TypeScript and will use ReactJS, NextJS, and SCSS

* Status: Accepted
* Deciders: Eric Hasegawa
* Date: 2023-04-03

## Context and Problem Statement

The first thing to build is a basic webapp to handle our frontend interface. We obviously need to decide what to use to build this,
before we start building it.
## Decision Drivers <!-- optional -->

* Webapp is necessary for essentially any kind of company.
* Frameworks, libraries, and other tools used to build on the web come and go quickly, so choosing libraries with a long-shelf life,
  good support, and vibrant communities is important.
* Webapps often act as the face of a company, so they must be efficient, pretty, and scalable.

## Considered Options

For languages:
* Ruby on Rails + JS
* Vanilla JS
* TypeScript (TS)

For styling:
* Vanilla CSS
* SCSS
* Tailwind
* Bootstrap

For frameworks/libraries:
* React JS
* React JS + Next JS
* Angular
* Vue
* Svelte

## Decision Outcome
We'll be using TS with ReactJS and NextJS, with styling handled in SCSS.
I want to use TS to avoid all of ambiguity with JS' type system, and to prevent bugs from reaching production.
ReactJS is the most popular framework by a significant margin with the largest community and huge amounts of support.
Performance from competitors is similar, and no other framework can guarantee better performance.
NextJS is recommended for use with ReactJS and is the largest, most supported option to enable server-side rendering and 
avoid the pitfalls associated with building a single-page application.
SCSS enables more powerful design and styling than traditional CSS, and adds effectively unlimited flexibility.

### Positive Consequences <!-- optional -->

* Great community and documentation surrounding all four products.
* Common stack, so if we are having troubles, plenty of bigger companies will be too.
* Strong performance when optimized correctly.
* Will be supported for a long time.

### Negative Consequences

* TS is newer than JS and will pose new problems that less people have experienced.
* A Ruby on Rails application would likely ship faster.
* Manual, traditional styling takes longer than using a library like Tailwind or Bootstrap.

## Evaluation of each option

### Ruby on Rails

* Ships quickly, strong community, well-loved language.
* Designed to handle basically a full application, one of the guiding principles of World0
  is that we should make architectural decisions that are easy to change. If we chose Rails, 
  that would effectively determine the structure of our whole product.
* Smaller community than other languages, harder to recruit for.

### JavaScript

* Battle-tested, most popular language on earth.
* Really extremely incredibly annoying.
* Hard to debug; tolerates too much ambiguity for my liking (we want to crash fast whenever something is wrong).

### TypeScript

* Superset of JavaScript, so it supports all JS with added typing.
* Prevents bugs from reaching production, catches things earlier, eliminates ambiguity.
* Smaller community, not supported by all technologies.

### Tailwind/Bootstrap

* Speed up development process and make styling easier.
* Limit flexibility in design.
* All Bootstrap apps seem to look the same.

### CSS/SCSS

* SCSS is more powerful than CSS but has a higher learning curve and must be compiled down. 
  For me, the extra power is worth it.
  
### Angular

* Heavier than React, and implements all three parts of the MVC, leaving us with less flexibility in the future. 
* Smaller, angrier community than React.
* Shows more signs of slowing down than React.

### Vue

* Great community, well-loved.
* Small community, tiny compared to the React ecosystem, I could see it falling 
  out of favor and being challenging to support and innovate with.
  
### Svelte
* Honestly a really strong contender and I can see Svelte growing quickly. It's simpler and lighter than React,
and has a happier community. However, it still has to prove its sticking power in the frontend community, and I 
don't want to take that risk given the long horizon of World0.

### ReactJS
* Huge community, most popular framework by far, has been in circulation for far longer than comparable products, and continues
to grow.
* Established conventions and thorough documentation, not just of official features, but of many common problems.
* Battle tested, performant, solid framework.
* Can be slow, requires add-ons to move past being a SPA.

### NextJS
* ReactJS now recommends using NextJS with it. 
* Allows bots and other automated services to crawl our webapp.
* Improves performance.
* Allows us to combine a hybrid static/dynamic website.
