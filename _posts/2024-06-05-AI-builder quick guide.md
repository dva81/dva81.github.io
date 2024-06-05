---
layout: post
title: Document Processing with AI Builder: A Practical Guide to the document automation toolkit
date: 2024-06-05
description: This blog post delves into the workings of the Document Automation Toolkit within AI Builder, detailing the steps involved in setting it up and the adjustments necessary to tailor it to specific needs.
categories: PowerPlatform AI
---

# Document Processing with AI Builder: A Practical Guide to the document automation toolkit

In today's fast-paced digital landscape, document automation is an essential tool for businesses looking to improve efficiency and accuracy. Microsoft’s AI Builder provides a comprehensive solution for automating document processing, integrating seamlessly with other Microsoft services like SharePoint and Teams. This blog post delves into the workings of the Document Automation Toolkit within AI Builder, detailing the steps involved in setting it up and the adjustments necessary to tailor it to specific needs.

## Getting Started: Out-of-the-Box Functionality
You can access the document automation toolkit in Power Automate.
Learn about the toolkit on [Document automation toolkit - AI Builder | Microsoft Learn](https://learn.microsoft.com/en-us/ai-builder/doc-automation) 

### 1. Setting Up the Solution

To begin, create a new solution within the AI Builder environment and import all necessary components. This step is straightforward, enabling users to swiftly set up a foundation for their document automation process.

### 2. Model Configuration
Next, create a simple model to complete the initial configuration steps within the app. This involves defining the types of documents to be processed and the data fields to be extracted.

### 3. Base Flow Testing
Test the base flow by integrating it with an email system. This initial test ensures that the basic document processing pipeline is functioning correctly.

### 4. Integrating File Imports
Adjust the flow to accommodate file imports from SharePoint or Teams. This integration allows for a seamless transition of documents from these storage solutions into the AI Builder processing pipeline.

## Customizing Features for Enhanced Usability

### 1. Enhancing the User Interface
The out-of-the-box user interface (UI) includes an interactive table, which may not be entirely user-friendly for all scenarios. To improve this, custom buttons and actions were created within the app, enhancing the overall user experience (UX) and making the toolkit more intuitive.
![image](https://github.com/dva81/dva81.github.io/assets/65031840/22280ec1-a86a-48e5-9f5a-f66a4463c785)

### 2. Overcoming Table Structure Challenges
In cases where a complex table structure needs to be extracted over multiple pages, the default capabilities of AI Builder might fall short. To address this, optical character recognition (OCR) and a series of regular expressions were employed. This combination allowed for the extraction of complex data structures from documents, ensuring no information was lost during processing.

### 3. Addressing Field Restrictions
The default character length restriction in Dataverse tables is set to for example 100 characters. For our model, longer field lengths were necessary. Adjusting these settings in Dataverse was possible but initially caused errors during testing. By tweaking these settings and running multiple tests, the issues were eventually resolved, allowing for smoother data processing.

### 4. Managing Bulk Deletion
Bulk deletion of documents is not supported out of the box. To manage this, a manual query was created for document deletion within Dataverse tables. This workaround ensured that unnecessary documents could be efficiently removed without manual intervention.

## Conclusion

Microsoft’s AI Builder Document Automation Toolkit offers robust features for automating document processing tasks. While the out-of-the-box functionalities provide a solid starting point, specific customizations and adjustments can significantly enhance usability and performance. By addressing UI challenges, overcoming complex table extraction issues, modifying field restrictions, and implementing manual deletion queries, businesses can tailor the AI Builder to meet their unique requirements, ensuring a more efficient and streamlined document automation process.

For those looking to delve deeper into document automation, exploring the full capabilities of AI Builder and making these tailored adjustments can unlock new levels of productivity and accuracy in managing documents.

My focus is on structuring, automating and managing business processes using Agile and DevOps best practices. This creates team working environments where business continuity, transparency and human capital come first. Reach out to me on LinkedIn or check out my GitHub for more tips and tricks.
