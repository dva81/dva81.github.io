---
layout: post
title: Document Processing with AI Builder - A Practical Guide to the document automation toolkit
date: 2024-06-05
description: This blog post delves into the workings of the Document Automation Toolkit within AI Builder, detailing the steps involved in setting it up and the adjustments necessary to tailor it to specific needs.
categories: PowerPlatform AI
---

In today's fast-paced digital landscape, document automation is an essential tool for businesses looking to improve efficiency and accuracy. Microsoft’s AI Builder provides a comprehensive solution for automating document processing, integrating seamlessly with other Microsoft services like SharePoint and Teams. This blog post delves into the workings of the Document Automation Toolkit within AI Builder, detailing the steps involved in setting it up and the adjustments necessary to tailor it to specific needs.

# Getting Started: Out-of-the-Box Functionality
You can access the document automation toolkit in Power Automate. Learn about the toolkit on [Document automation toolkit - AI Builder | Microsoft Learn](https://learn.microsoft.com/en-us/ai-builder/doc-automation). 
The inital installation is standard and next-next-finish. You do need some knowledge of Power Platform if you want to get started with this.  
The two installations I did stalled on the last step but everything looked in working order after a refresh of the browser. 

## 1. Setting Up the Solution
To begin, create a new solution within the Power Platform environment and import all toolkit components. The Toolkit comes as a managed solution, so this way you can make the necesary adjustments to the flow's, apps and dataverse tables. This step is straightforward, enabling users to swiftly set up a foundation for their document automation process.
![image](https://github.com/dva81/dva81.github.io/assets/65031840/6f6d19a2-4ba8-48f5-b961-6a53b5bc43bf)

## 2. Model Configuration
Next, create a simple model to complete the initial configuration steps within the app. This involves defining the types of documents to be processed and the data fields to be extracted.
![image](https://github.com/dva81/dva81.github.io/assets/65031840/9eb347fd-6b54-44da-833c-067df788d422)

## 3. Base Flow Testing
Test the base flow by integrating it with an email system. This initial test ensures that the basic document processing pipeline is functioning correctly.

Check and test the email importer flow
![image](https://github.com/dva81/dva81.github.io/assets/65031840/70e4aa74-1942-475f-8547-48d6892ab21c)

Configure the Power App to use the correct model. 
![image](https://github.com/dva81/dva81.github.io/assets/65031840/4d4fd77b-46be-4219-9fa6-5b3ecc7425d4)

Ready to go!
![image](https://github.com/dva81/dva81.github.io/assets/65031840/6b63ee00-ae52-4057-967d-47efda211e02)

## 4. Integrating File Imports
Adjust the flow to accommodate file imports from SharePoint or Teams. This integration allows for a seamless transition of documents from these storage solutions into the AI Builder processing pipeline.
For this I duplicated the email importer flow and adjusted the steps in the flow to retrieve the files from a sharepoint location. 

It took only a few hours to get the document automation application up and running. After processing a few documents a few opportunities for improvement emerged.

# Customizing Features for Enhanced Usability

## 1. Enhancing the User Interface
The out-of-the-box user interface (UI) includes an interactive table, which may not be entirely user-friendly for all scenarios like high volume input or table manipulation. To improve this, custom buttons and actions were created within the app, enhancing the overall user experience (UX) and making the toolkit more intuitive.
I added an add, delete and copy row button and a general save button. The copy function is great if lines have similar text in it and were not extracted properly. 
And the lay-out was tweaked a bit. The pdf viewer was made a bit smaller to allow for more room for the table and fields. 

![image](https://github.com/dva81/dva81.github.io/assets/65031840/22280ec1-a86a-48e5-9f5a-f66a4463c785)

## 2. Overcoming Table Structure Challenges
In cases where a complex table structure needs to be extracted over multiple pages, the default capabilities of AI Builder might fall short. To address this, optical character recognition (OCR) and a series of regular expressions were employed. This combination allowed for the extraction of complex data structures from documents, ensuring no information was lost during processing.

## 3. Addressing Field Restrictions
The default character length restriction in Dataverse tables is set to for example 100 characters. For our model, longer field lengths were necessary. Adjusting these settings in Dataverse was possible but initially caused errors during testing. By tweaking these settings and running multiple tests, the issues were eventually resolved, allowing for smoother data processing.

![image](https://github.com/dva81/dva81.github.io/assets/65031840/8d4fa078-950d-4176-a25f-3801a5f67ecd)

## 4. Managing Bulk Deletion
Bulk deletion of documents is not supported out of the box. To manage this, a manual query was created for document deletion within Dataverse tables. This workaround ensured that unnecessary documents could be efficiently removed without manual intervention.

# Conclusion

Microsoft’s AI Builder and Document Automation Toolkit offers robust features for automating document processing tasks. While the out-of-the-box functionalities provide a solid starting point, specific customizations and adjustments can significantly enhance usability and performance. By addressing UI challenges, overcoming complex table extraction issues, modifying field restrictions, and implementing manual deletion queries, businesses can tailor the AI Builder to meet their unique requirements, ensuring a more efficient and streamlined document automation process.

My focus is on structuring, automating and managing business processes using Agile and DevOps best practices. This creates working environments where business continuity, transparency and human capital come first. Reach out to me on [LinkedIn](https://www.linkedin.com/in/dennisvanaelst) or check out my [github](https://github.com/dva81) or [blog](https://www.dennisvanaelst.net/) for more tips and tricks.

----
The ideas and underlying essence are original and generated by a human author. The organization, grammar, and presentation may have been enhanced by the use of AI.



