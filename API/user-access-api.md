---
layout: page
title: API Strategy - User Access & Provisioning
permalink: /portfolio/user-access-api/
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
Retrieves a list of all active users and their assigned Conga/Salesforce permission sets.

### **Request**
`GET /v2/access/users`

**Query Parameters:**
| Parameter | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| `status` | String | No | Filter by `active` or `inactive`. |
| `license_type` | String | No | Filter by `conga_sign`, `conga_composer`, or `salesforce`. |

**Example Request:**
`GET https://api.yoursystem.com/v2/access/users?status=active&license_type=conga_sign`

### **Response**
**Success (200 OK)**
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
    },
    {
      "user_id": "u_7741",
      "name": "Jane Smith",
      "email": "jsmith@example.com",
      "permissions": ["Conga Composer User"],
      "last_login": "2025-12-15T09:15:00Z"
    }
  ]
}