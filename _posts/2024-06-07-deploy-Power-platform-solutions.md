---
layout: post
title: Azure DevOps - Easily deploy a Power platform solution
date: 2024-06-10
description: In this article I am sharing my take on deploying a Power Platform Solution across environments. How to use a repo, build pipeline and release to different environments.
categories: PowerPlatform AI DevOps
---

# Azure DevOps : Easily deploy a Power platform solution

I have been a Azure DevOps enthousiast for years. The ease of use, flexibility of the platform are super. In this article I am sharing my take on deploying a Power Platform Solution across environments.
How to use a repo, build pipeline and release to different environments.

## Repos
There is no need to download the solution in a repo if you are not going to manipulate the source / zip file. Using the repo for the deployment settings file is a good practice as these are configurations that are not managed in the solution. 
![image](https://github.com/dva81/dva81.github.io/assets/65031840/9ed4499a-b617-44de-9df4-0c93aeb1bd00)

## Pipelines  - build artifact
I see pipelines as a means to create a deployable artifact of deployable item. So for me it should only have the steps to collect and package the components that need to be deployed.
![pipeline actions](https://github.com/dva81/dva81.github.io/assets/65031840/674d2575-bf4e-4d2b-8230-dc44428dd29c)

![artifact content](https://github.com/dva81/dva81.github.io/assets/65031840/8502521d-d641-4a56-b9ea-ff25f860f638)
 
## Pipelines  - Release 
the release 

Also check out this post if you like Azure DevOps! [Boosting Efficiency Docs-as-Code Strategies with Power Platform and Azure DevOps](https://www.dennisvanaelst.net/blog/2023/Docs-as-Code/)


