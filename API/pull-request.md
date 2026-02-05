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
```

### Response Example (202 Accepted)
Since data synchronization can take a moment, the API returns an acknowledgment with a `sync_id`.
```json
{
  "status": "processing",
  "sync_id": "sync_998877",
  "message": "Data pull initiated successfully."
}
```

---

## Status Codes (Salesforce Sync)
Use this guide to troubleshoot the results of your Salesforce data pull:

| Status Code | Meaning | Outcome |
| :--- | :--- | :--- |
| **202 Accepted** | **Sync Started** | The request is valid and the data pull from Salesforce is now in progress. |
| **400 Bad Request** | **Invalid Fields** | One or more fields requested (e.g., `BillingStreet`) do not exist on that Salesforce object. |
| **401 Unauthorized** | **Auth Failed** | Your Bearer Token is invalid or has expired. |
| **404 Not Found** | **Record Missing** | The specific Salesforce `record_id` could not be found in the connected org. |
| **429 Too Many Requests** | **Rate Limit** | You have exceeded the Salesforce API daily limit. Try again later. |

---