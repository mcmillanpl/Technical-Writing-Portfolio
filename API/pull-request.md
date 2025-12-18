---
layout: page
title: API Strategy - Salesforce Integration (Pull Requests)
---

# Pull Request API (Salesforce)

## Overview
The Pull Request API allows external systems to trigger and monitor data synchronization between Salesforce and Conga Sign. This ensures that any "Pull" request for data from a Salesforce record into a contract is logged and tracked for compliance.

## Base URL
`https://api.contractgen.com/v1`

## Authentication
All requests require a **Bearer Token** passed in the HTTP Authorization header.

`Authorization: Bearer {YOUR_API_TOKEN}`

---

## Endpoint: Initiate Pull Request
`POST /v1/salesforce/pull`

Triggers a request to fetch specific record data from Salesforce.

### **Request Body**

| Parameter | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| `record_id` | String | Yes | The Salesforce ID (e.g., `0015e00000XjYzA`). |
| `object_type` | String | Yes | The Salesforce object (e.g., `Account`, `Opportunity`). |
| `fields` | Array | Yes | List of fields to retrieve. |

**Example Request:**
```json
{
  "record_id": "0015e00000XjYzAAV",
  "object_type": "Account",
  "fields": ["Name", "BillingStreet", "Phone"]
}