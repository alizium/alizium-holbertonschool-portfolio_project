# Stage 3 – Technical Documentation  
## Task 4: External and Internal APIs  

---

## 1. External APIs  

Expiry Tracker uses an external email provider to send reminder notifications and account emails.  

### Example: SendGrid (or Mailgun)  
- **Purpose:** Outbound email delivery for reminders and account emails.  
- **Reason chosen:** Reliability, scalability, analytics.  
- **Integration:** Backend calls the provider’s REST API with JSON payloads, using API key stored in environment variables.  

---

## 2. Internal API (Expiry Tracker REST API)  

**Base URL:** `/api/v1`  
**Authentication:** Bearer JWT in the `Authorization` header.  
**Content-Type:** `application/json`  

---

### 2.1 Authentication  

#### Register a new user  
- **URL:** `/api/v1/auth/register`  
- **Method:** `POST`  
- **Input (JSON):**  
```json
{
  "username": "john_doe",
  "email": "john@example.com",
  "password": "securePassword123"
}
```  
- **Output (JSON):**  
```json
{
  "user": {
    "id": 1,
    "username": "john_doe",
    "email": "john@example.com"
  },
  "accessToken": "eyJhbGciOiJIUzI1NiIsInR..."
}
```  

---

#### Login  
- **URL:** `/api/v1/auth/login`  
- **Method:** `POST`  
- **Input (JSON):**  
```json
{
  "email": "john@example.com",
  "password": "securePassword123"
}
```  
- **Output (JSON):**  
```json
{
  "user": {
    "id": 1,
    "username": "john_doe",
    "email": "john@example.com"
  },
  "accessToken": "eyJhbGciOiJIUzI1NiIsInR..."
}
```  

---

### 2.2 Documents  

#### List all documents  
- **URL:** `/api/v1/documents`  
- **Method:** `GET`  
- **Output (JSON):**  
```json
{
  "items": [
    {
      "id": 42,
      "name": "Passport",
      "category": "Administration",
      "issue_date": "2015-12-10",
      "expiry_date": "2025-12-10",
      "status": "expiring",
      "notes": "Renew 1–2 months early"
    }
  ]
}
```  

---

#### Add a new document  
- **URL:** `/api/v1/documents`  
- **Method:** `POST`  
- **Input (JSON):**  
```json
{
  "name": "Passport",
  "category": "Administration",
  "issue_date": "2015-12-10",
  "expiry_date": "2025-12-10"
}
```  
- **Output (JSON):**  
```json
{
  "id": 102,
  "name": "Passport",
  "category": "Administration",
  "issue_date": "2015-12-10",
  "expiry_date": "2025-12-10",
  "status": "expiring"
}
```  

---

### 2.3 Reminders  

#### Create a reminder  
- **URL:** `/api/v1/reminders`  
- **Method:** `POST`  
- **Input (JSON):**  
```json
{
  "document_id": 102,
  "notify_at": "2025-11-10T09:00:00Z"
}
```  
- **Output (JSON):**  
```json
{
  "id": 501,
  "document_id": 102,
  "notify_at": "2025-11-10T09:00:00Z",
  "status": "pending"
}
```  

---

## 3. Error Codes  

- `400` – Bad Request  
- `401` – Unauthorized  
- `403` – Forbidden  
- `404` – Not Found  
- `409` – Conflict  
- `500` – Internal Server Error  

---

## 4. Security Notes  

- Passwords are hashed with bcrypt/argon2.  
- JWT tokens are short-lived.  
- Input validation and sanitation on all endpoints.  
- Ownership checks for all user resources.  
