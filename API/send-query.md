---
layout: page
title: API Strategy - Salesforce Query Service
---

# Send Query API v1.0

## Overview
The Send Query API allows developers to programmatically execute SOQL (Salesforce Object Query Language) queries. This service is essential for fetching dynamic data to populate contract templates and verify record integrity before generation.

## Base URL
`https://api.contractgen.com/v1`

## Authentication
All requests require a **Bearer Token** passed in the HTTP Authorization header.

`Authorization: Bearer {YOUR_API_TOKEN}`

---

## Endpoint: Execute Query
`POST /v1/salesforce/query`

Executes a specific query against the connected Salesforce instance.

### **Request Body**

| Parameter | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| `query` | String | Yes | The SOQL query string to execute. |
| `include_metadata` | Boolean | No | Whether to return field metadata in the response. |

**Example Request:**
```json
{
  "query": "SELECT Name, AccountNumber FROM Account WHERE Industry = 'Technology'",
  "include_metadata": false
}