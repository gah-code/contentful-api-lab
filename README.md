# 📦 Contentful API Lab

For Contentful API Lab — Developer Playground

This lab serves as a sandbox environment for developing, testing, and refining the API-driven content architecture behind my website [IN PROGRESS](https://github.com/gah-code/gilbertoharosite). It focuses on dynamic data fetching from Contentful, modeling structured content types such as blog posts and soon-to-be-portfolio projects, and ensuring smooth CRUD operations through tools like Postman. The lab will support real-time CMS updates via webhooks to maintain a scalable, developer-friendly, and production-ready content pipeline.

---

## 🛠️ Project Approach & Developer Workflow Guide

This guide outlines how to model content in **Contentful**, fetch and manipulate it using the **Content Delivery and Management APIs**, and streamline testing and development via **Postman**.

---

## 📘 Postman Integration Guide - IN PROGRESS

## 📂 Folder Descriptions

### 📄 **Blog Post Endpoints**

**Purpose:**  
This folder contains all **CRUD operations** related to the `blogPost` content type in Contentful. These requests help developers manage blog content directly via API — including fetching, creating, updating, publishing, and deleting blog entries. It serves as the primary workspace for integrating blog data with a frontend (e.g., for rendering posts in Next.js or Astro).

**Key Uses:**

- Retrieve blog posts by slug (for dynamic routing)
- Create and publish new content from Postman
- Update or remove existing posts during testing or migration
- Automate content workflows using Content Management API

---

### 📚 **Content Model Introspection**

**Purpose:**  
This folder provides endpoints to **inspect your Contentful content model**, including fetching metadata about content types and fields. It's essential for developers planning schema-aware implementations — like dynamic forms, content-driven components, or styling systems using tools like `vanilla-extract`.

---

### 🧠 Get All Content Types (Schema Overview)

---

### 🔍 Get Specific Content Type (e.g. blogPost)

---

### 🔧 Use Case: Planning `vanilla-extract` Mappings
