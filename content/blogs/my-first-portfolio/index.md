+++
title = "Launching My First Portfolio"
date = 2025-09-13T13:15:00Z
draft = false
description = "How I built my first portfolio using Hugo and the Congo theme."
summary = "How I built my first portfolio using Hugo and the Congo theme."
tags = ["portfolio", "hugo", "congo", "webdev"]
+++

I’m really excited to share my very first **portfolio website**, built with [Hugo](https://gohugo.io/) and the [Congo theme](https://github.com/jpanther/congo). 🎉  

This portfolio is a big step for me — it will serve as a place to showcase my projects, write posts, and share my journey in tech.  

---

## Why Hugo + Congo?  

- **Hugo** is a super-fast static site generator. Once I learned the basics, it became much easier to structure my site.  
- **Congo** is a clean, minimal, and customizable theme that works perfectly for portfolios and blogs.  

---

## Setup Commands  

Here are some of the key commands I used to get my portfolio up and running:  

```bash
# Create a new Hugo site
hugo new site my-portfolio

# Move into the new site
cd my-portfolio

# Initialize Hugo modules (instead of using git submodules)
hugo mod init github.com/yourusername/my-portfolio

# Add the Congo theme
hugo mod get github.com/jpanther/congo/v2

# Copy the example config from Congo
cp -r themes/congo/config/_default config/_default

# Run the development server
hugo server
