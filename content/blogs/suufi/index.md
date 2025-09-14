+++
title = "Building and Deploying Sufii"
date = 2025-09-13T15:00:00Z
draft = false
description = "How I built and deployed the Sufii website using MongoDB, GitHub, and Cloudflare Pages."
tags = ["sufii", "webdev", "mongodb", "cloudflare", "deployment", "ci-cd"]
+++

Today I worked on a project called **Sufii**, a website that combines a database backend with a simple deployment workflow.  

---

## Project Summary (Front Matter in Context)  

- **Title**: The post title highlights the project name — *Sufii*.  
- **Date**: Marks when the work was done and the post was written.  
- **Description**: Provides a one-line overview for readers and search engines.  
- **Tags**: Help organize posts by technology (MongoDB, Cloudflare, CI/CD, etc.).  

This way, anyone browsing my portfolio can quickly understand what the project is about before even opening the full post.  

---

## Tech Stack  

- **MongoDB** for storing and managing data  
- **GitHub** for version control and hosting the code  
- **Cloudflare Pages** for hosting and automatic deployments  

---

## Workflow  

### 1. Setting Up the Database (MongoDB)  
I used **MongoDB** to handle the backend data. This gave me a flexible and scalable way to store and retrieve information for the site.  

### 2. Version Control with GitHub  
All project files were pushed to a **GitHub repository**. This ensures version control and also makes deployment smoother with Cloudflare Pages.  

### 3. Deploying with Cloudflare Pages  
On the **Cloudflare dashboard**, I:  
- Linked my **GitHub account** to Cloudflare  
- Selected the **Sufii repository** from my account  
- Configured build settings (framework/build command/output directory)  
- Left **Continuous Integration (CI)** and **Continuous Deployment (CD)** in Cloudflare’s hands  

From here on, whenever I push changes to GitHub, Cloudflare automatically rebuilds and redeploys the site globally.  

---

## The Result  

With MongoDB managing the data, GitHub handling version control, and Cloudflare automating deployments, **Sufii** was up and running quickly.  

This combination of tools made development smooth and deployment hassle-free. 🚀  
