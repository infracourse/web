---
title: Final Project
toc: false
---

**Due Sunday, March 17, 11:59 PM PT**

You will deploy a web application to AWS such that it could feasibly be used at scale by a nontrivial quantity of users. The project is designed to showcase your understanding of cloud concepts and ability to tie together multiple cloud services with infrastructure-as-code. We recommend you complete the final project in a group of two.

While we encourage you to be creative and deploy custom applications you may have written, the necessary development skills to do so are out-of-scope for the course. Final projects that deploy existing web or network software in a way that takes advantage of cloud services to meet the demands of scale still satisfy requirements and are eligible to receive full credit.

**Note**: We're publicizing the below as requirements that your final project must fulfill. We will shortly add a grading rubric, some more example project ideas (which you may use directly). Later in the quarter, we'll also publish submission instructions for the project.

## Examples

You may use any of these examples as your final project directly. Feel free to chat with us at office hours or after class if you would like any feedback on your project idea.

* Run a Minecraft server, which may include the following components:
  - Backups
  - Databases for the application and for certain plugins
  - DNS
  - Security policies for exposed resources
  - Logging
* Run a Wordpress instance for hosted content such as a blog
* Run a Shynet instance for privacy-preserving web analytics

An example writeup for Yoctogram is available [here](/assignments/project/yoctogram-example-writeup.pdf).

## Architecture Requirements

* ~~Entire infrastructure deployment must be contained within an AWS CDK project~~ Entire infrastructure deployment must be done using IaC
  - An exception is made for any potential interactions with the CS40 DNS provisioner if used
  - The course staff cannot guarantee their ability to assist with any IaC framework except AWS CDK
* A multilayer architecture, including separate application and data layers
  - This means no static web apps
* Elasticity (must efficiently scale up/down to match user demand)
  - Your application should not be grossly overprovisioned by default
  - This can be achieved using services like Fargate, Lambda, Aurora, Auto Scaling Groups, etc.
* Load distribution for performance
  - This includes load balancing like the built in AWS ELB/ALB, CDNs like Cloudfront, etc.
* Reasonable security
  - No secrets in the frontend!
  - Proper segmentation of subnets
  - Reasonable security groups
  - Reasonable IAM policies
* DNS/TLS properly configured for endpoints
  - Includes frontend and backend if necessary for CORS
* Observability for monitoring key metrics
  - AWS Cloudwatch, Datadog, etc.

## Deliverables

We expect the following components:

* A way to access the deployed application – ideally has DNS and TLS configured
* A .zip file containing the source code to the CDK project used to deploy the application
* A short report detailing the cloud services that were used, how they interoperate,  difficulties encountered, and takeaways learned from the deployment.
  - This report should include an architecture diagram
