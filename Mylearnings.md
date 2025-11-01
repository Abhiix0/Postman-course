
````markdown
# 🚀 Postman Mastery — Beginner to Advanced  

> Course: [Postman Beginner’s Course - freeCodeCamp](https://youtu.be/VywxIQ2ZXw4)  
> Duration: ~2 hours  
> Goal: Master API testing, automation, and documentation in Postman.

---

## ⚙️ 1. Postman Setup & Interface

- Installed Postman and explored the workspace layout:
  - **Sidebar:** Collections, Environments, History  
  - **Request builder:** URL bar, Params, Headers, Body, Tests  
  - **Console:** For debugging logs and responses  
- Created my first request (`GET https://reqres.in/api/users`).

🧠 Tip: The console is your best friend — use it to see raw request/response logs.

---

## 🌐 2. Sending Requests

### **GET**
- Retrieves data.  
- Can include **query parameters** like `?page=2`.

### **POST**
- Creates new data using JSON body.  
```json
{
  "name": "Abhi",
  "job": "student"
}
````

### **PUT / PATCH**

* Updates existing data.

### **DELETE**

* Deletes specific data.

🔍 Checked **status codes** (`200 OK`, `201 Created`, `204 No Content`, etc.) for validation.

---

## 🧩 3. Collections

* Collections = organized folders for requests.
* Grouped all my API calls into one **collection** for cleaner workflow.
* Collections can store:

  * Requests
  * Tests
  * Variables
  * Documentation

📦 Exported collections as `.json` to share or use with Newman.

---

## 🔑 4. Authorization

* Learned 4 main types:

  * **No Auth**
  * **API Key**
  * **Bearer Token**
  * **Basic Auth**
* Example for token-based API:

  1. Hit login endpoint → receive `access_token`
  2. Use token in header automatically with `Authorization: Bearer <token>`

✅ Postman can **store tokens in environment variables** and auto-inject them into future requests.

---

## 🌍 5. Environment Variables

* Defined reusable variables like:

  ```text
  {{base_url}} = https://reqres.in
  {{auth_token}} = xyz123
  ```
* Different **environments** for Dev, Staging, and Prod.
* Helps avoid hardcoding — just switch environments.

💡 Types of variables: Global, Environment, Collection, Local.

---

## ⚗️ 6. Tests (JavaScript)

* Postman supports **JS test scripts** after each request.
* Example:

  ```js
  pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
  });
  ```
* Extract values from responses:

  ```js
  const res = pm.response.json();
  pm.environment.set("userId", res.id);
  ```
* Reuse extracted variables in the next requests with `{{userId}}`.

🧠 Built a small chain of dependent requests using these dynamic variables.

---

## 🔄 7. Collection Runner

* Runs all requests in sequence automatically.
* Supports multiple iterations + data from CSV/JSON.
* Example use: test an API flow from login → fetch → delete.

```js
postman.setNextRequest("Fetch User"); // Move to next request dynamically
```

---

## 📊 8. Monitors & Scheduling

* Created a **monitor** to run a collection daily.
* Used it to check uptime for APIs.
* Added notifications if response time exceeded limits.

---

## 💻 9. Newman (CLI for Postman)

* Installed via:

  ```bash
  npm install -g newman
  ```
* Ran collections from the command line:

  ```bash
  newman run my_collection.json
  ```
* Generated reports:

  ```bash
  newman run my_collection.json --reporters cli,htmlextra
  ```

🔗 This is how Postman integrates with CI/CD tools.

---

## 🧠 10. Documentation

* Wrote **auto-generated API documentation** in Postman.
* Published a live doc link for my collection.
* Useful for team sharing or public API references.

---

## ✅ What I Can Do Now

* Test any REST API (GET, POST, PUT, DELETE)
* Handle Auth (Tokens, Keys, Basic)
* Use Variables & Environments efficiently
* Write JS Tests for automation
* Run Collections using Runner or Newman
* Generate API Docs & Monitors

---
