# Our web frontend will be hosted using AWS.

* Status: Accepted
* Deciders: Eric Hasegawa
* Date: 2023-04-11

## Context and Problem Statement

Where are we going to host and deploy our front-end webapp?

## Decision Drivers <!-- optional -->

* We need to host/deploy our webapp somewhere.
* Different options have vastly different consequences and trade-offs.

## Considered Options

* Vercel
* Netlify
* Heroku
* GCP, Azure etc.
* AWS

## Decision Outcome

Chosen option: AWS due to cost-effectiveness at scale, control over infrastructure, and general flexibility.

### Positive Consequences <!-- optional -->

* We won't need to switch over to AWS once we scale.
* We control our CICD and infrastructure.
* We won't be paying for things we don't need or use.

### Negative Consequences <!-- optional -->

* Setup is much more complicated.
* We don't get the nice built-in tools of expensive options.
* Generally a lot more work on our end.

## Pros and Cons of the Options

### Vercel, Netlify, Heroku

* Vercel builds NextJS so they are well-positioned to host it.
* Excellent products that would make our lives much easier.
* Expensive at scale: seem to trap companies in their growth phase and then lay on the costs.


### GCP, Azure etc.

* Similar to AWS but less-used/documented.

### AWS

* Cost-effective and pricing does not skyrocket at scale.
* Integrates with other AWS services that we use.
* Allows for maximum control and flexibility.
* Much more complicated to setup and run.
* Requires us to manually set up CICD etc.
* Limited free-tier compared to Vercel, Netlify etc.

Note that deciding to use AWS actually says relatively little about how we are going to host. Even within AWS there are a myriad of
options for web-hosting, from managed solutions like Amplify and Lightsail to fully independent ones like simple EC2 instances or Docker containers on ECS.
This decision does not say anything about how we will use AWS to host, that will come in a later decision.
