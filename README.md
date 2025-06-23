# 🧪 Gorest API Testing – Postman Collection

This Postman collection automates testing of basic **CRUD operations** (Create, Read, Update, Delete) using the [GoREST API](https://gorest.co.in/).

---

## 📦 Collection Overview

**Collection Name**: `Gorest_api_testing`

This collection contains 4 key requests:

1. **Create New User**  
2. **Get User Details**
3. **Update Username**
4. **Delete User**

It also uses **Pre-request Scripts** and **Test Scripts** to set dynamic data, store IDs, and validate responses.

---

## 🔐 Authorization

- **Type**: Bearer Token  
- **Token Variable**: `{{token}}` (Automatically set in the pre-request script)

---

## 📌 Environment Variables

| Variable   | Description                          |
|------------|--------------------------------------|
| `token`    | GoREST API token                     |
| `QA`       | Base URL of the API (e.g. `https://gorest.co.in/public/v2/users`) |
| `id`       | Stores user ID created dynamically   |
| `userName` | Generated random username            |
| `emailId`  | Generated random email ID            |

---

## 🔄 Request Descriptions

### 1. ✅ `Create New User` (POST)
- Dynamically generates a username and email.
- Sends a POST request to create a new user.
- Stores the returned `id`, `userName`, and `emailId` in environment variables.
- Verifies:
  - HTTP status is `201 Created`
  - `Content-Type` header is present and `application/json`

### 2. 🔍 `User Details` (GET)
- Retrieves user details using the stored `id`.

### 3. 📝 `Update Username` (PUT)
- Updates the user's name using the stored `id`.

### 4. ❌ `Delete User` (DELETE)
- Deletes the user using the stored `id`.
- Clears all relevant environment variables.

---

## ⚙️ How to Use This Collection

1. **Import the JSON File** into Postman.
2. Set the environment variables (`token`, `QA`) or use the included `Pre-request Script`.
3. Run requests one by one, or automate using a **Collection Runner**.
4. Validate response data through the built-in **Tests**.

---

## 🔒 Sample Authorization Header

```http
Authorization: Bearer {{token}}
