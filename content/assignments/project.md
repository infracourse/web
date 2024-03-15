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
* Run an open-source CMS like Wordpress, Joomla, or Drupal for managing website content or blogging
* Run a Shynet instance for privacy-preserving web analytics
* Run a forum using software like Discourse or Flarum, or a self hosted Wiki like MediaWiki
* Run a project management tool like Redmine or Taiga
* Run an IRC server like UnrealIRCd
* Run a demo/toy application with a more complex microservice architecture such as those [from this list](https://github.com/davidetaibi/Microservices_Project_List/blob/master/README.md#demotoy--projects-mainly-for-learning-or-research-purpose)

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
* ~~Observability for monitoring key metrics~~ Observability requirement has been relaxed.  An observability solution is still highly encouraged but no longer required.
  - ~~AWS Cloudwatch, Datadog, etc.~~

## Deliverables

We expect the following components:

* A way to access the deployed application – ideally has DNS and TLS configured
* The source code of all IaC used to deploy application.  If a custom web app, submit web app code as well.
* A short report detailing the cloud services that were used, how they interoperate,  difficulties encountered, and takeaways learned from the deployment.
  - This report should include an architecture diagram
* Include links to any code/web, tutorials, guides, Github repos, or any other resources used

## Submission Instructions

On Gradescope, there are two assignments:

* Final Project Writeup: submit a PDF of your report here
  - This is where you will be able to view your final grade for the final project.  Don't worry about page selection-- we'll read the whole thing.
* Final Project Code: submit the IaC used to deploy your app.  If a custom web app was deployed, include the code of the custom web app.
  - The code itself will not receive a grade, this assignment is merely a way to submit your code to us for grading.

Leave your web app up until *after* 11:59 on Tuesday, March 3/26 (the final deadline for posting grades).  If you have insufficient credits to keep your assignment up this long, make a private Ed post.

Congratulations on finishing CS 40!  Thank you for your support in the first year we are offering this class!
