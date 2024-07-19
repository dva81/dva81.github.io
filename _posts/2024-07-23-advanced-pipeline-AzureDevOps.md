---
layout: post
title: Skills vs Connectors in Microsoft Copilot Studio - Making the Right Choice
date: 2024-07-23
description: This article provides a foundational understanding to help you navigate the choice between Skills and Connectors in Microsoft Copilot Studio. 
categories: PowerPlatform AI DevOps Copilot
---

# A more advanced pipeline in Azure DevOps for Power Platform solutions.

When working with many developers or designers in highly secure environment with a lot of compliance rules and regulations, Power Platform can be challenging to maintain. In this [Azure DevOps: Easily deploy a Power platform solution | LinkedIn]{https://www.linkedin.com/pulse/azure-devops-easily-deploy-power-platform-solution-dennis-van-aelst-mzfpe/?trackingId=Zt9plSeCTg2OyehjOFpuog%3D%3D}   article, I gave an example on how to create a simple DevOps pipeline. 
This time I will show you two advanced pipeline to export and import a Power Platform solution with a GITHUB connection.
The thought behind this is that the highly regulated enterprises have more complex working environments and needs. 
- Many developers are working on the same solution in different development environments. 
- Code or configuration check must be done before deploying preferably automated
- Branching and merging policies.
- Standard configurations must be added automatically after development

## Setting the stage
We will be using the following components. 
- Azure DevOps environment for the build and release pipelines
- GITHUB repository for storing the configuration and merging the different brances
- Power Platform environment with a solution to export 

The example will be importing from only one environment but it can be extended if needed.
If you are reading this article, I can safely assume you know your way around Microsoft Power Platform. However source control is not always related to low code so if you are new to GITHUB check out this Beginner's guide to GitHub repositories: How to create your first repo - The GitHub Blog

## Build 
There are two pipelines. Get the Solution and Pack and drop branches
![image](https://github.com/user-attachments/assets/5dd9d6ee-4239-458a-a15f-5a0e658ed683)

### Get the Solution 
The goal is to export the solution from the Power Platform environment and store the configuration in GITHUB under a new branch.
 ![image](https://github.com/user-attachments/assets/1ca58311-b0c7-4854-a3b3-99b42f81540f)

The first three jobs are simple but before those start the Checkout – job creates / clones the Github repo on the agent. This way we can use that location to clean the repository before unpacking the solution in that location.
![image](https://github.com/user-attachments/assets/48762fd5-985f-4876-a374-871ae7cd5893)

In the Clean repo step, The GIT rm command is used to remove the old configuration making it ready to accept the new incoming.
 ![image](https://github.com/user-attachments/assets/801024a4-f39b-4178-bbdc-bca224ed6750)

After unpacking, we can send the file to GITHUB in a new branch. I am using predefined variables Predefined variables - Azure Pipelines | Microsoft Learn because I like standard basic things.
 
### Things did not go as planned
Some things took more time than others. These types of things are an intricate maze of configurations and settings.
The Git push did not work and I got a message the “authentication was not done properly”. I missed a setting in the Agent Job.
 
git - Azure Pipeline, Cannot prompt because terminal prompts have been disabled - Stack Overflow


 

Error Not a repo: This was because I cleaned the repo before filling it again. I solved this with the GIT rm command. Which did not destroy the cloned repo.
Solved: fatal: Not a git repository (or any of the parent directories): .git (komodor.com)

Unpack vs unzip does not make a difference.
What is strange is that the [Content_types].xml is not extracted in both cases and files in the root are placed in the folder ‘other’

 
 
 
 
 
 
 

After packing it creates the correct structure again… 

# Pack and drop branches

 
# Release pipelines
The  release pipelines is easy. We are working with managed solutions. Unmanaged is not advised!
Microsoft considers these as still under development, and you can import or export as unmanaged. You can modify unmanaged solutions.
Managed solutions are complete solutions ready for distribution that you cannot modify after importing them to the selected environment. These solutions are intended for production environments. 
More info on: Solution layers - Power Apps | Microsoft Learn

 
By using the managed solution all your environments stay nice and clean. 
Here is an example of a multi stage environment. You can even make this dynamic if you incorporate pipelines and scripts for environment provisioning and use the API for Azure DevOps to automatically create pipelines and release configurations.
 

# A parting note
I did not show the deployment settings in the example. Check out my other article for that. You are merging configuration not real code, the Power Platform is not really intended to use this way.  

My focus is on structuring, automating and managing business processes using Agile and DevOps best practices. This creates working environments where business continuity, transparency and human capital come first. Reach out to me on LinkedIn or check out my github or blog for more tips and tricks.
----
The ideas and underlying essence are original and generated by a human author. The organization, grammar, and presentation may have been enhanced by the use of AI.
