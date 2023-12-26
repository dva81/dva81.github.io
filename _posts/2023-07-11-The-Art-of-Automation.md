---
layout: post
title:The Art of Automation: Crafting Automatic Responses with Power Platform and AI
date: 2023-07-11 
description: When a friend recently approached me with a question about personal productivity, I found myself thinking, 'I can certainly offer some guidance on that.'
tags: Power Platform
categories: Power Platform
related_posts: false
---

When a friend recently approached me with a question about personal productivity, I found myself thinking, 'I can certainly offer some guidance on that.'

This was her initial message to me:

> From November I will not work on Wednesdays (my daughter is going to school, and I am taking parental leave). Is there a way my account will send automatic replies, saying our office is closed, when I receive emails on Wednesday? Or do I have to reset this every Wednesday?

The way this is described is not a standard outlook feature to my knowledge and research. I wanted to use this example [Smart Out of Office with Power Automate (updated May 2021) (linkedin.com)](https://www.linkedin.com/pulse/smart-out-office-microsoft-flow-marc-de-kleijn) but then I saw this new feature in Power Automate and I wanted to give it a go. Microsoft Power Automate is an online workflow service that automates actions across the most common apps and services.

Describe it to design it... How does it work?

This AI-powered feature uses a language model to create a cloud flow from a description. The model understands natural language input and writes the code for the flow. This experience uses GPT-3 as a foundation to understand a natural language prompt and generate a working cloud flow.

Step 1: Copy - Paste - Send

I copy/pasted the message I got via chat and clicked on send.

![The Art of Automation]('assets\img\The Art of Automation\The Art of Automation (1).png')

  
The first suggestion it gave was not really what I was looking for. It could work but, in my opinion, it did not cover the complete scenario.

![The Art of Automation]('assets\img\The Art of Automation\The Art of Automation (2).png')

![The Art of Automation]('assets\img\The Art of Automation\The Art of Automation (3).png')
Step 2: Do it again

So, I tried again. Iteration two.

This time I prompted: monitor my mailbox. if I get an email and it is Wednesday reply with an email that says I am not available on Wednesdays. A bit simpler, more straightforward. Notice I put in an if statement to guide the engine."

![The Art of Automation]('assets\img\The Art of Automation\The Art of Automation (4).png')

![The Art of Automation]('assets\img\The Art of Automation\The Art of Automation (5).png')

This time it made a suggestion that could be a good start. I put a proper reply message and started the flow test. This whole process took about 10 minutes.

It may look like a super easy way to create flows, which it is, but I know the Power Platform, can write code and know how to write a decent ChatGPT prompt to get result I can work with. It is my belief that you need to know basic programming structures and have some coding skill to get a decent output out of any AI-powered tool or low-code platform.

This is a great assistant for workflow designers, but it does not replace them.

That said, I installed the process, my friend made some notes and changed the email message and does not have to worry about her autoreply again. Mission accomplished!

Have look at this free online workshop if you are interested in Personal Productivity and automation.

[Power Automate: Automation - Online Workshop - Training | Microsoft Learn.](https://learn.microsoft.com/en-us/training/paths/robotic-process-automation-online-workshop/)