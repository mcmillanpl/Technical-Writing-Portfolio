# User Access API v2.1

## Overview
The User Access API allows administrators to audit and manage user permissions across the **Salesforce** and **Conga** environments. This ensures compliance with security protocols and streamlines the onboarding/offboarding process.

## Base URL
`https://api.contractgen.com/v2`

## Authentication
All requests require a **Bearer Token** passed in the HTTP Authorization header.

`Authorization: Bearer {YOUR_API_TOKEN}`

---

## Endpoint: List User Permissions
`GET /v2/access/users`

Retrieves a list of all active users and their assigned Conga/Salesforce permission sets.

### **Query Parameters**

| Parameter | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| `status` | String | No | Filter by `active` or `inactive`. |
| `license_type` | String | No | Filter by `conga_sign` or `salesforce`. |

### **Response Example (200 OK)**
The API returns a `users` array containing detailed permission sets and `last_login` data.

```json
{
  "total_results": 1,
  "users": [
    {
      "user_id": "u_9982",
      "name": "Pamela McMillan",
      "email": "mcmillan.pld@gmail.com",
      "permissions": ["Conga Sign Admin", "Salesforce User"],
      "last_login": "2025-12-18T10:30:00Z"
    }
  ]
}
```

---

## Rate Limiting
To ensure system stability and security, the User Access API is subject to administrative rate limits. If you exceed these limits, the API will return a `429 Too Many Requests` status.

* **Limit:** 100 requests per minute per Admin Token.
* **Window:** Sliding 60-second window.

### **Updated Status Codes (Access API)**

| Status Code | Meaning | Outcome |
| :--- | :--- | :--- |
| **200 OK** | **Success** | The list of users was retrieved successfully. |
| **401 Unauthorized** | **Auth Failed** | Your Bearer Token is invalid or expired. |
| **403 Forbidden** | **Insufficient Privileges** | Your account does not have "Admin" rights to view user access lists. |
| **429 Too Many Requests** | **Rate Limit** | You have exceeded the administrative request quota. Please wait 60 seconds. |
| **500 Internal Error** | **Server Error** | An unexpected error occurred. Please contact Conga Support. |

---