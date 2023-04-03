# Use ADRs to track important decisions.

* Status: Accepted <!-- optional -->
* Deciders: Eric Hasegawa
* Date: 2023-04-03

## Context and Problem Statement

How are we going to track what decisions have been made throughout the lifetime of the project, and how those decisions were reached?

## Decision Drivers

* Recording why and how decisions have been made is important for understanding why a system is designed the way it is.
* Decisions are made at a specific point in time from a specific context, what was a good decision under a specific set of 
  circumstances can become a poor decision as those circumstances change. Knowing the rationale and reasoning behind the original
  decision allows us to understand when it should be changed or iterated upon.
* Explicitly documenting decisions will lead them to be better.

## Considered Options

* Using a template in Google Docs, Notion, or some software along those lines.
* Leave out ADRs until the scope of the project is better-defined.
* Use a Github repository to store and manage ADRs.

## Decision Outcome

We'll be using a Github repository to track ADRs. Github allows a large amount of customizability and extensibility, so we can format
ADRs exactly how we want, add additional content when necessary, and integrate the decision log with the rest of our source code. It also makes
decisions feel like they are made not at some abstract high level far away from our codebase (which could lead to an 
[ivory tower architecture](https://www.oreilly.com/library/view/software-architects-handbook/9781788624060/d4ff9836-0ca4-4889-9e7c-71800c17156a.xhtml)), 
but instead are made relatively close to where they will be implemented.

### Positive Consequences <!-- optional -->

* Architectural decisions will be more thoughtful and deliberate.
* Future contributors will understand the rationale behind decisions.
* When re-evaluating a past-decision, we can reference the original reasoning behind it to see if it's still relevant.

### Negative Consequences <!-- optional -->

* Documenting decisions takes time and could slow down development.
* Logging decisions in a Github repository makes them less accessible to non-technical staff.
