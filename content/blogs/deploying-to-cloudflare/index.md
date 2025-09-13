+++
title = "Deploying My Portfolio with Cloudflare Pages"
date = 2025-09-13T14:00:00Z
draft = false
description = "How I deployed my Hugo + Congo portfolio using Cloudflare Pages."
summary = "How I deployed my Hugo + Congo portfolio using Cloudflare Pages."
tags = ["portfolio", "hugo", "congo", "cloudflare", "deployment", "ci-cd"]
+++

After building my portfolio with **Hugo** and the **Congo theme**, the next step was to get it online. For this, I chose **[Cloudflare Pages](https://pages.cloudflare.com/)**. 🚀  

---

## What is Cloudflare Pages?  

Cloudflare Pages is a **JAMstack platform** for deploying static websites directly from your GitHub or GitLab repository. It automatically builds and deploys your site whenever you push changes — no servers to manage, no manual uploads.  

Some benefits include:  
- Free and fast global CDN  
- Automatic builds with continuous integration (CI)  
- Continuous deployment (CD) for every push  
- Easy GitHub/GitLab integration  

---

## Steps I Followed  

### 1. Linked My GitHub Account  
On the Cloudflare Pages dashboard, I linked my **GitHub account** so that Cloudflare could access my repositories.  

### 2. Selected My Repository  
From the list of repositories, I selected the one that contained my Hugo + Congo portfolio.  

### 3. Configured Build Settings  
Cloudflare Pages recognized that my site used **Hugo**. I simply confirmed the defaults:  
- **Framework preset**: Hugo  
- **Build command**: `hugo`  
- **Output directory**: `public`  

### 4. Continuous Integration + Deployment  
The best part: I don’t have to deploy manually anymore. Cloudflare Pages automatically:  
- Runs the build process whenever I push changes to GitHub  
- Deploys the updated version to a global CDN  
- Provides a live URL and even preview deployments for branches  

---

## The Result  

Within a few minutes, my portfolio was live on the web — and every update I push to GitHub now goes live automatically. 🙌  

This setup makes it easy for me to focus on writing content and improving my site, while **Cloudflare handles deployment in the background**.  

---

✅ Next, I’ll be writing about how I plan to organize and publish posts here — stay tuned!  
