# We will be using KeyCloak to handle authentication and authorization

* Status: Accepted
* Deciders: Eric Hasegawa
* Date: 2023-04-04

## Context and Problem Statement

How are we going to handle user authentication and authorization? This is the first actually hard decision given that I have no idea what kind of users we'll have
(i.e. if we'll be targeting other businesses using SSO or direct consumers logging on with Google/FB/Twitter). The auth space is quite complicated and different
companies have _hugely_ different offerings. Our focus here is to choose a provider that allows us the flexibility to have different kinds of users in the future,
while also not costing us too much.

## Decision Drivers <!-- optional -->

* Every software application has users.

## Considered Options

* KeyCloak
* Okta
* Auth0
* AWS Cognito
* Firebase
* Supabase
* MS Azure
* JumpCloud
* Authress
* Rolling our own

## Decision Outcome

Chosen option: KeyCloak due to it's flexibility, scalability, and affordability. KeyCloak is open source and doesn't host itself, so we'll be self-hosting it.
This could be a pain in the ass, but it'll scale in a much more affordable way, and will also allow us to handle SSO, AD, social login etc. without having to use
multiple vendors. There isn't an auth platform that I'm entirely satisfied with, but with the current information I have (which is basically one day of research) and
the ambiguity of the project, KeyCloak is our best bet.

### Positive Consequences

* We can handle user sign-up/login
* We can handle SSO, LDAP/AD, Identity brokering etc. when we need to.
* Open source!
* We won't go bankrupt paying $0.25 per user per month with Auth0.
* We own our user data, not Google or some other service.

### Negative Consequences

* Self-hosting will require more human capital than using a managed service.
* Might be more expensive initially to host a whole server for this.
* Sets us up with an auth platform before we know what we even need it for.

## Pros and Cons of the Options <!-- optional -->

### Okta/Auth0

* Really great service with strong UI, extensibility, support etc.
* SO expensive.

### AWS Cognito

* Very well priced and fits nicely into the AWS ecosystem.
* Terrible documentation, limited to being single-region, hated by users.
* AWS doesn't seem to care about it so it has a ton of issues.

### Firebase

* Cheap and easy to setup.
* Locks you into Google's options (limited flexibility).
* Google owns your user data.

### Supabase

* Actually looks really awesome, great concept.
* Unproven (really new), only used by startups.
* Requires buy-in to their DB system (harder to change in future).

### MS Azure

* Some great options for auth.
* Seems to focus more on B2B companies.
* Works best within the Azure ecosystem.


### Jump Base

* Good pricing and solid product.
* Doesn't focus on B2C needs.
* Mostly designed for auth _within_ an organization.
* Seems to be built for authorization, not necessarily authentication.

### Authress

* Strong option, but focuses more on B2B needs.
* No one seems to use it?

Ultimately, KeyCloak has so much flexibility, which is really what we need given the uncertainty of our roadmap.
