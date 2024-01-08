---
layout: post
title: Automating LinkedIn Posts - A Simple Scheduler for Busy Professionals
date: 2024-01-11
description: Many professionals dedicate time to post regularly or leverage scheduling functions to maintain a consistent online presence. However, when it comes to bulk scheduling posts, LinkedIn lacks a native feature, leaving you in need of a customized solution.
categories: PowerPlatform
---


As a practice lead, staying active on LinkedIn is crucial for promoting both yourself and your business. Many professionals dedicate time to post regularly or leverage scheduling functions to maintain a consistent online presence. However, when it comes to bulk scheduling posts over an extended period, LinkedIn lacks a native feature. Even the LinkedIn API falls short in this aspect, leaving you in need of a customized solution.

In my quest to efficiently manage my LinkedIn content, I decided to create a simple scheduler that allows me to plan my posts for the next two years. In this blog post, I'll walk you through the process of building a Power Automate Flow that meets this requirement.

# Requirements
- Dynamic Message Creation: Ensure variation in posts to keep your content engaging.
- Bi-weekly Scheduling: Automate the process to post every two weeks.
- Maintain Control: Craft a solution that keeps you in the driver's seat.

# Building the Power Automate Flow
![Automating LinkedIn Posts](/assets/img/Automating LinkedIn Posts/Automating LinkedIn Posts (3).png)

## Step 1 Connect with LinkedIn
The first step involves creating a connection with LinkedIn using the standard free connector. Simply use your credentials to log in and establish the connection.
![Automating LinkedIn Posts](/assets/img/Automating LinkedIn Posts/Automating LinkedIn Posts (2).png)

## Step 2 Dynamic Message Creation
To add variety to your posts, leverage Power Automate's functions. Utilize the rand function to dynamically generate messages, ensuring a mix of content in your posts.
![Automating LinkedIn Posts](/assets/img/Automating LinkedIn Posts/Automating LinkedIn Posts (5).png)

![Automating LinkedIn Posts](/assets/img/Automating LinkedIn Posts/Automating LinkedIn Posts (1).png)

##  Step 3 Bi-weekly Scheduling
Implement a scheduling mechanism within the flow to post every two weeks. This ensures a consistent presence on your LinkedIn profile.
![Automating LinkedIn Posts](/assets/img/Automating LinkedIn Posts/Automating LinkedIn Posts (4).png)

Step 4 Stay in Control
The entire solution is designed to keep you in control. By dynamically creating messages, scheduling bi-weekly posts, and leveraging Power Automate's capabilities, you can confidently manage your LinkedIn content for the next two years.

# Access the Power Automate Flow
To implement this solution, you can download the source files directly from [GitHub](https://github.com/dva81/PowerAutomate). Don't forget to turn the flow on after setting it up.

Empower your LinkedIn strategy by taking charge of your posting schedule with this simple yet effective Power Automate Flow. Stay visible, stay engaged, and let automation work for you!

 
