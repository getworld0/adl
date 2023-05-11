# Our web frontend will be hosted on Vercel

* Status: Accepted, supercedes [#0004-host-web-aws](https://github.com/getworld0/adl/blob/main/0004-host-web-aws.md).
* Deciders: Eric Hasegawa
* Date: 2023-05-10 <!-- optional -->

## Context and Problem Statement

Where are we going to host and deploy our front-end webapp?


## Decision Drivers
We need to host/deploy our webapp somewhere.
Different options have vastly different consequences and trade-offs.

## Considered Options
* Vercel
* Netlify
* Heroku
* GCP, Azure etc.
* AWS

## Decision Outcome

Chosen option: Vercel since deploying on AWS is actually _more_ expensive at small scale, and is infinitely more complicated.


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
*
### Note on why ADR 0004 was superceded.
I fiddled with various AWS deployments for over 2 weeks (on and off) trying to find something that is manageable and affordable. We could always
just run the site on an AWS instance or something, but that costs real money and makes our lives harder; the more complex options mainly
leveraged serverless architectures and containers, but these were incredibly complex and would take a _very_ long time to properly set up. 

I know right now this is basically an over-engineered `hello-world` project, and having this scalable infrastructure is the whole point of this, but trying
to set up a scale-to-infinity web deployment right off the bat was too complicated for me. I know that web-hosting is something we'll have to come back and change
later, but setting up deployment on Vercel took all of about ten minutes, so it will be very easy to change :)
