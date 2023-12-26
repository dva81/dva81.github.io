---
layout: post
title: Boosting Efficiency Docs-as-Code Strategies with Power Platform and Azure DevOps
date: 2023-12-12
description: Some time ago I took over a Power Platform project right after first deploys to production. The application is a collection of over 30 Power Apps and more than 600 other components. With my DevOps background I was really happy to see the Azure DevOps setup the team had put in place to automate the deploy of the hundreds of Power Platform components as much a as possible.
tags: DevOps
categories: DevOps
---

Some time ago I took over a Power Platform project right after first deploys to production. The application is a collection of over 30 Power Apps and more than 600 other components. With my DevOps background I was really happy to see the Azure DevOps setup the team had put in place to automate the deploy of the hundreds of Power Platform components as much a as possible.

If you want to see how that can be done check out this video by Feline Parein. [Feline Parein - How to deploy Power Platform solution company-wide: Azure DevOps can help with CI/CD - YouTube](https://www.youtube.com/watch?v=pv8CyKrL5ds)

As I was new to the project, I had no context to inform my understanding of what was going on or how things were connected. So, I started reading and looking for information. The developers were working on all the new features and releases, so they had little time to address my information needs.

# Why docs-as-code?

I found a maze of documents, snippets, designs and much more without any solid structure. Everything was there but it was in chaos. After talking to the team, I found out that, like most developers they don't like to write documentation, switching tools and work environments, there was no review process, and they did not see the purpose of it as "everything we build is Low-Code".

> My next mission was clear: improve the process, improve the documentation.

With docs-as-code, you treat your documentation in the same way as your code. A quick start: 

- Format: pick a format that is easily versioned and transformed like .md. (Markdown)

- Versioning: Use a versioning system like GIT just as you would with code or configuration files. No need to append a date or v2.2x at the end. 

- Automation: Transform the docs to any format needed (html, pdf, ...) and distribute them in one go.

- Validation: Use an approval flow to get the documents approved and signed off.

# How did we do this?

The good thing was the team already tried to put documentation in repositories. We built on those first steps and completed the process. 

- Create a wiki and publish it as code

![publish it as code]('assets/img/Docs-as-Code/Docs-as-Code (1).png')

- .md as format. Markdown is a lightweight markup language that you can use to add formatting elements to plaintext text documents. 

![publish it as code]('assets/img/Docs-as-Code/Docs-as-Code (2).png')
![publish it as code]('assets/img/Docs-as-Code/Docs-as-Code (3).png')

- In the pipeline step the output is generated in pdf format using a standard task in Azure DevOps. and attached to the artifact for deployment. 

![publish it as code]('assets/img/Docs-as-Code/Docs-as-Code (4).png')

- Releasing the documentation. In this step we automated the release to the right location for validation. After approval in Azure Devops that version was copied to the end user or production locations in the Power Platform solution. 

![publish it as code]('assets/img/Docs-as-Code/Docs-as-Code (6).png')
![publish it as code]('assets/img/Docs-as-Code/Docs-as-Code (5).png')

# Bringing it all together

> "Happy cows make better milk." 

By improving the overall documentation process, the team is now much more inclined to write documentation and maintain it. Connecting other people to the project is now much easier and we created better continuity for our client as well.

---

Have look at this Microsoft Power Platform Build Tools for Azure DevOps - Power Platform | Microsoft Learn. 

If you are more interested in the view of a technical writer, you might want to start your journey at http://writethedocs.org.

---

My focus is on structuring, automating and managing business processes using Agile and DevOps best practices. This creates team working environments where business continuity, transparency and human capital come first. Reach out to me on LinkedIn or check out my GitHub for more tips and tricks.
