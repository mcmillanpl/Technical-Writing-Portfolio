---
layout: page
title: API Strategy - User Access & Provisioning
---

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
```json
{
  "total_results": 2,
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