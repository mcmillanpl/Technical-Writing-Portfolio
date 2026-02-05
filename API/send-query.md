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

Executes a specific `query` against the connected Salesforce instance.

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
```

### Response Example (200 OK)

The API returns a records array containing the results of your query.
```json
{
  "total_size": 1,
  "done": true,
  "records": [
    {
      "Name": "TechCorp Inc.",
      "AccountNumber": "TC-990"
    }
  ]
}
```

## Status Codes (Query API)
| Status Code | Meaning | Outcome |
| :--- | :--- | :--- |
| **200 OK** | **Success** | The query was executed successfully and results are in the `records` array. |
| **400 Bad Request** | **SOQL Syntax Error** | The query string is malformed (e.g., a misspelled field or missing `FROM` clause). |
| **401 Unauthorized** | **Auth Failed** | Your Bearer Token is invalid, expired, or lacks query permissions. |
| **403 Forbidden** | **Permission Error** | Your Salesforce user does not have access to the requested Object or Fields. |
| **500 Internal Error** | **Timeout/Limit** | The query was too complex or exceeded Salesforce governor limits. |