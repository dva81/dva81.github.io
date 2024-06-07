---
layout: post
title: Azure DevOps - Easily deploy a Power platform solution
date: 2024-06-10
description: In this article I am sharing my take on deploying a Power Platform Solution across environments. How to use a repo, build pipeline and release to different environments.
categories: PowerPlatform AI DevOps
---

# Azure DevOps : Easily deploy a Power platform solution

I have been a Azure DevOps enthousiast for years. The ease of use, flexibility of the platform are super. In this article I am sharing my not-so-complex take on deploying a Power Platform Solution across environments.
I will explain how to use a repo, build pipeline and release to different environments.

## Repos
There is no need to download the solution in a repo if you are not going to manipulate the source / zip file. Using the repo for the deployment settings file is a good practice as these are configurations that are not managed in the solution. This way you do have version control over the het deployment settings. The solution versions are managed in Power Platform or you can revert from the artifact 

![image](https://github.com/dva81/dva81.github.io/assets/65031840/9ed4499a-b617-44de-9df4-0c93aeb1bd00)

## Pipelines  - build artifact
I see pipelines as a means to create a deployable artifact of deployable item. So for me it should only have the steps to collect and package the components that need to be deployed. You can either schedule this or start this manually if you are ready to deploy.

![pipeline actions](https://github.com/dva81/dva81.github.io/assets/65031840/674d2575-bf4e-4d2b-8230-dc44428dd29c)

![artifact content](https://github.com/dva81/dva81.github.io/assets/65031840/8502521d-d641-4a56-b9ea-ff25f860f638)

As you can see this package contains everything you need to deploy to any environment. So even if you want to revert the development environment you can do it with this package.
 
## Pipelines  - Release 
The release stages are set up from the build output / artifact. Everything is there so no need for other sources. In this example we have three environment to deploy to and this can be across tenants if needed. We use the service connections for the connections. 

![release stages](https://github.com/dva81/dva81.github.io/assets/65031840/96a44216-f9fd-4ec3-8ab2-7828c6861566)

As far as actions go. Always install the tool on the agent and import the solution using the json we configured.

![stage actions](https://github.com/dva81/dva81.github.io/assets/65031840/9ef2c0b1-f4e7-4589-bc81-546229476b69)

![deployment settings](https://github.com/dva81/dva81.github.io/assets/65031840/0f5fb92b-1154-436f-8821-8336a7ca3347)

# That's it. No need to overcomplicate.

Hope this helps! Feel free to contact me on LinkedIn 
Also check out this post if you are interessed in Azure DevOps! [Boosting Efficiency Docs-as-Code Strategies with Power Platform and Azure DevOps](https://www.dennisvanaelst.net/blog/2023/Docs-as-Code/)



