+++
title = "Initiating the Sufii API Project"
date = 2025-09-13T16:00:00Z
draft = false
description = "An overview of the first steps in building the Sufii API with Node.js, Express, MongoDB, and Cloudflare R2."
summary = "Kicking off the Sufii API project: setting up Node.js + Express with MongoDB, adding middleware for file uploads to Cloudflare R2, and implementing the first artists endpoint."
tags = ["sufii", "nodejs", "express", "mongodb", "cloudflare", "api", "backend"]
+++

Today marks the beginning of the **Sufii API Project**, an API that will eventually power an ecosystem of **Suufi (of the Tijanniyya sect) products**. This is the foundation stage, where we have put together the initial structure, tools, and first endpoints.  

---

## Tech Stack  

- **Node.js + Express** → backend framework  
- **MongoDB** → database setup  
- **Cloudflare R2** → object storage (S3-compatible) for profile images  
- **AWS SDK for JavaScript (v3)** → to interact with R2 storage  

---

## Project Setup  

We initialized the backend and organized the project into standard folders for scalability:  

- `controllers/`  
- `services/`  
- `helpers/`  
- `models/`  
- `routes/`  
- `middlewares/`  
- `config/`  

This structure will make it easier to extend and maintain as the API grows.  

---

## Features Implemented So Far  

### 1. Middleware for Profile Image Uploads  
- Implemented an upload flow where **Multer** first attaches the file to the request object.  
- Added a **middleware** to push uploaded images to **Cloudflare R2**, using `@aws-sdk/client-s3` since R2 is **S3-compatible**.  

### 2. Artist Resource (First Endpoint)  
- Built out the **controller**, **service**, and **route** for the first resource: `artists`.  
- This marks the first official endpoint of the API.  

### 3. Manual Testing with Postman  
- Verified endpoints using **Postman** to ensure the routes, controllers, and services were all wired correctly.  

---

## Current Status  

At this stage, we have:  
- A **working project structure**  
- Middleware for **file uploads to Cloudflare R2**  
- The **first resource (artists)** implemented and tested  

---

## Next Steps  

- Add more resources to the API  
- Expand middleware and helper functions  
- Set up automated testing for endpoints  
- Prepare deployment workflows (possibly through **Cloudflare Pages/Workers** in future)  

---

This is just the beginning of the Sufii API. Each update will bring us closer to powering the wider ecosystem of Suufi products. 🚀  
