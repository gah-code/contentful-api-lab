
# 📘 Postman Integration Guide DRAFT

*For Contentful API Lab — Developer Playground*

This guide helps developers **use Postman effectively** to explore and manage Contentful-powered content models — with a focus on the `blogPost` type and schema-driven design planning.

---

## 📂 Folder Descriptions

### 📄 **Blog Post Endpoints**

**Purpose:**  
This folder contains all **CRUD operations** related to the `blogPost` content type in Contentful. These requests help developers manage blog content directly via API — including fetching, creating, updating, publishing, and deleting blog entries. It serves as the primary workspace for integrating blog data with a frontend (e.g., for rendering posts in Next.js or Gatsby).

**Key Uses:**

- Retrieve blog posts by slug (for dynamic routing)
- Create and publish new content from Postman
- Update or remove existing posts during testing or migration
- Automate content workflows using Content Management API

---

### 📚 **Content Model Introspection**

**Purpose:**  
This folder provides endpoints to **inspect your Contentful content model**, including fetching metadata about content types and fields. It's essential for developers planning schema-aware implementations — like dynamic forms, content-driven components, or styling systems using tools like `vanilla-extract`.

**Key Uses:**

- Explore all content types in your space
- Retrieve the full schema for a single content type (e.g., `blogPost`)
- Plan frontend data mappings based on field types
- Support future automation like code generation or token mapping

---

## 📚 Content Model Introspection Endpoints

### 🧠 Get All Content Types (Schema Overview)

**Method:** `GET`  
**URL:**

```
https://api.contentful.com/spaces/{{space_id}}/environments/{{environment_id}}/content_types
```

**Headers:**

```
Authorization: Bearer {{management_token}}
```

---

### 🔍 Get Specific Content Type (e.g. blogPost)

**Method:** `GET`  
**URL:**

```
https://api.contentful.com/spaces/{{space_id}}/environments/{{environment_id}}/content_types/blogPost
```

**Headers:**

```
Authorization: Bearer {{management_token}}
```

---

### 🔧 Use Case: Planning `vanilla-extract` Mappings

With this data, you can:

- Auto-generate component fields based on content model definitions
- Create tokenized design maps for each content field
- Plan style variations (e.g. `title`, `tags`, `featuredImage`) based on field types (`Short text`, `Rich text`, `Media`)

---

## 📄 Blog Post Endpoints

### 🟦 Get Blog Post by Slug

**Description:**  
Fetch a single blog post based on its unique `slug`. Useful for dynamic routing and pre-rendering pages in frameworks like Astro or Next.js.

**Method:** `GET`  
**URL:**

```
https://cdn.contentful.com/spaces/{{space_id}}/environments/{{environment_id}}/entries?content_type=blogPost&fields.slug={{slug}}
```

**Headers:**

```http
Authorization: Bearer {{access_token}}
```

**Required Environment Variables:**

| Variable         | Description                         |
|------------------|-------------------------------------|
| `space_id`       | Your Contentful Space ID            |
| `environment_id` | Usually `master`, or your custom env |
| `access_token`   | Content Delivery API Token (read)   |
| `slug`           | The slug of the blog post you're querying |

**Example Response (Trimmed):**

```json
{
  "items": [
    {
      "fields": {
        "title": "My First Blog Post",
        "slug": "my-first-post",
        "content": { "nodeType": "document", ... },
        "publishDate": "2025-04-22T00:00:00Z"
      }
    }
  ]
}
```

---

## ✅ Current Postman Folder Structure

```
📦 Contentful API Lab (Collection)
│
├── 📄 Blog Post Endpoints
│   ├── Get All Blog Posts ✅
│   ├── Get Blog Post by Slug ✅
│   ├── Create New Blog Post
│   ├── Publish Blog Post
│   ├── Update Blog Post
│   └── Delete Blog Post
│
└── 📚 Content Model Introspection
    ├── Get All Content Types
    └── Get blogPost Schema
```

---

 next request: **Create New Blog Post**.
