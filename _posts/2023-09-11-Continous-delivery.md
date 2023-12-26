---
layout: post
title: Continuous delivery with EMC Captiva document capture software
date: 2023-05-10
description: Setting up a continuous delivery environment can be a daunting task, especially when working with third party software. In this blog post, Dennis Van Aelst and Stef Kusters provide some insight in using EMC Captiva in a continuous delivery environment.
tags: Capture, DevOps
categories: Capture, DevOps
related_posts: false
---

Setting up a continuous delivery environment can be a daunting task, especially when working with third party software. In this blog post, Dennis Van Aelst and Stef Kusters provide some insight in using EMC Captiva in a continuous delivery environment.

# What is EMC Captiva?

The EMC Captiva products are used to automate document capture and enterprise capture in other words to automatically digitize paper documents such as files or letters. With EMC Captiva, information that was stored on paper becomes easily accessible in content management systems.

# What is continuous delivery and what are the benefits?

A continuous delivery environment is set up to optimize development processes: it focuses on rapid development and deployment of bite-sized pieces of software.

In practice, that means that developers work on the software on their own workstations, while the continuous delivery system takes care of versioning, testing and deploying their work. It reduces the amount of manual tasks, which improves the quality of development and deployment, while reducing unnecessary stress during deployment.

Setting up this environment requires a fundamental change in the process, technologies used and mindset of all parties involved. In this post, we ll focus on the process and technologies, as hanging the mindset of people is a different (and much more subjective) challenge, which probably deserves its own blog post.


# How we set up a continuous delivery process

In this post, we ll use the process we created for one of our customers as an example. The image below shows how the set-up of the continuous delivery environment.

These are the main steps in this set-up:

1.      Developers work at their workstations with Captiva Designer and commit code to the GIT repository

2.      Creation of an artifact with Jenkins in Artifactory

3.      Testing, acceptance and push to production (the live environment) with Nolio

4.      Automated testing using UFT

# Step 1: development in Captiva Designer and commitment to GIT


The first step in the process, as shown in the image above, is the developers working on their workstations. They use the Captiva Designer to make changes to the development environment as they please. When they are done, the developers commit their code to the GIT repository. GIT is primarily used for version control in this set-up.

If you d like a more detailed description of this step, please read our [blog post on the EMC Community blog](http://community.emc.com/people/dennisvanaelst/blog/2016/06/21/how-to-use-captiva-in-a-continuous-delivery-environment).

# Step 2: Creation of an artifact with Jenkins in Artifactory

In this second step, we focus on version control and getting our deployment configuration in Artifactory using Jenkins. We use GITBLIT as a repository and Tortoise as an interface for the developer.

After this step Jenkins kicks off the Nolio process and deployment to the test environment is on its way.

A more in-depth description of this step can be found in this [blog post](http://community.emc.com/people/dennisvanaelst/blog/2016/06/27/how-to-use-captiva-in-a-continuous-delivery-environment-using-git-and-jenkins).

# Step 3: Testing, acceptance and push to production with Nolio


 Nolio is a configurable release management tool that can be used to deploy to multiple environments and create the automatic deployment scripts, replacing the manual cookbook.

The setup we made only uses the deployment part for automating various steps in the deploy process. With Powershell or something similar you can achieve the same thing. We have a template in Nolio for deploying these configurations behind this template are multiple Nolio processes with all the steps needed to deploy processes or profiles or configuration items.

# Step 4: Using UFT for automated testing


At the end of the deployment process, we kick off an automated test using Unified Functional Testing (HP). This test creates a batch by importing images, then indexes them and verified the data in Captiva. We added a web service which automatically looks up values in the batch and compares them to the expected values. That way we can easily create 100 or more test cases.

The content of this blog post appeared across various blog posts by Dennis Van Aelst and Stef Kusters on the [EMC Community blog](http://community.emc.com/people/dennisvanaelst/content?filterID=contentstatus%5Bpublished%5D~objecttype~objecttype%5Bblogpost%5D) first in October, 2016
