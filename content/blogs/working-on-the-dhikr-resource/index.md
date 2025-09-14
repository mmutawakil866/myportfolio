+++
title = "Implementing the Dhikr Resource"
date = 2025-09-13T17:00:00Z
draft = false
description = "Building the Dhikr resource for the Sufii API with MongoDB, worker threads, ffmpeg, yt-dlp, and Cloudflare R2."
summary = "We added the Dhikr resource to the Sufii API: setting up a schema in MongoDB, handling audio uploads with worker threads, processing video and links into audio, and integrating Cloudflare R2 storage."
tags = ["sufii", "nodejs", "express", "mongodb", "cloudflare", "api", "dhikr", "ffmpeg", "yt-dlp", "worker-threads"]
+++

After setting up the **artists resource**, we shifted focus to a new and more complex one: **Dhikr**, which is heavily dependent on audio files.  

---

## Schema Setup  

We started by defining the **Mongoose schema** for dhikr documents in MongoDB:  

```js
const mongoose = require("mongoose");

const dhikrSchema = new mongoose.Schema(
  {
    title: { type: String, required: true },
    description: { type: String },
    artist: { type: String },

    listens: { type: Number, default: 0 },
    likes: { type: Number, default: 0 },
    likedBy: { type: [String] },
    tags: { type: [String] },
    duration: { type: Number },

    status: {
      type: String,
      enum: ["processing","failed","pending","verified"],
      default: "processing",
    },

    uploadedType: {
      type: String,
      enum: ["link","audio","video"],
    },

    link: { type: String },
  },
  { timestamps: true }
);

module.exports = mongoose.model("Dhikr", dhikrSchema);
```

This schema captures not only metadata (title, description, artist, tags, etc.) but also the file type, status, and interaction metrics (likes, listens).  

---

## Controller + Service Setup  

We created a **controller file** and a **service file** for Dhikr.  
All business logic lives in the service layer, while the controller just coordinates requests and responses. This code splitting makes the project easier to maintain and extend.  

---

## `createDhikr` Endpoint  

Our first endpoint was `createDhikr`. Here’s how we designed it:  

- It accepts `multipart/form-data` with both **metadata** and an **audio file**.  
- Because audio files can be large, we used **Node.js worker threads** to offload file processing to a separate worker.  
- We accounted for **three upload types**:  
  - **Audio** → directly uploaded to Cloudflare R2  
  - **Video** → processed with **ffmpeg** to extract audio  
  - **Link** → processed with **yt-dlp** to download audio from YouTube (or other supported platforms)  

Once processed, the resulting audio file is uploaded to **Cloudflare R2** for storage.  

---

## Swapping Audio Files  

We also added an endpoint to **swap out old audio files**:  

- The old file is deleted from **Cloudflare R2**  
- A worker thread uploads the new file  
- The **MongoDB document is updated** with the new file reference  

---

## Current Status  

At this stage, the **Dhikr resource** supports:  
- Schema for saving dhikr documents in MongoDB  
- A `createDhikr` endpoint that handles audio, video, and links  
- Worker-based processing for large file uploads  
- R2 storage integration for finalized audio files  
- An endpoint to **replace existing audio files** safely  

---

This is a big milestone for the **Sufii API**, as Dhikr will be one of the core resources in the ecosystem. 🎧  