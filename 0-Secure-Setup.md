
# 🔐 Contentful Postman Environment – Secure Setup

This Postman environment is pre-configured for safely interacting with your **Contentful space** using both the Content Delivery API (CDA) for read operations and the Content Management API (CMA) for create, update, and delete operations.

It follows best practices for securely managing API tokens and environment variables, enabling you to quickly test and manage blog content.

---

## ✅ Environment Variables

| Variable         | Description                                                  |
|------------------|--------------------------------------------------------------|
| `space_id`       | Your Contentful space identifier                             |
| `env_id`         | Environment ID (usually `master`)                            |
| `cdn_url`        | Base URL for the Content Delivery API                        |
| `access_token`   | **Secret** token for authentication (CMA)                    |
| `entry_id`       | Optional: Target entry ID for updating, publishing, or deleting |

> 💡 **Security Tip**: Use the `Current Value` field for `access_token` in Postman. Leave the `Initial Value` empty to avoid exposing secrets in shared exports.

---

## 🚀 Setup Instructions

### 1. Import the Environment

1. In Postman, go to the **Environments** tab.
2. Click **Import** and select the file:  
   📁 `postman-env-contentful-gcode-filled.json`

### 2. Set the Secret Token

1. Locate the `access_token` variable.
2. Paste your **Content Management API token** into the **Current Value** field.
3. Ensure that **Initial Value** is left blank.

---

## 🧪 Example: Python Script (GET Entry via CMA)

Use this Python script to retrieve a Contentful entry using the CMA:

```python
import requests

SPACE_ID = "your_space_id"
ENV_ID = "master"
ENTRY_ID = "your_entry_id"
ACCESS_TOKEN = "your_management_token"

url = f"https://api.contentful.com/spaces/{SPACE_ID}/environments/{ENV_ID}/entries/{ENTRY_ID}"
headers = {
    "Authorization": f"Bearer {ACCESS_TOKEN}",
    "Content-Type": "application/vnd.contentful.management.v1+json"
}

response = requests.get(url, headers=headers)

if response.status_code == 200:
    print("✅ Entry Retrieved:")
    print(response.json())
else:
    print(f"❌ Error {response.status_code}: {response.text}")
```

> 🧠 Tip: For security, consider loading `ACCESS_TOKEN` from a `.env` file using `python-dotenv`.

---

## 📦 Files Included

- `postman-env-contentful-gcode-filled.json` – Secure Postman environment setup
- `README.md` – This guide

---

## 🧠 Next Steps

- Pair this with a CRUD-ready [Postman Collection](#) for creating, publishing, or deleting entries
- Use `entry_id` and `version` dynamically via Postman scripting or Python automation
- Consider setting up Dev and Prod environments in Postman

---

## 👨‍💻 Maintained by

Gilbert Haro  
GitHub: [@gah-code](https://github.com/gah-code)

---
