---
layout: page
title: API Strategy - ContractGen REST API
permalink: /portfolio/api-sample/
---

# ContractGen REST API v1.0

## Overview
This API allows developers to programmatically generate and track legal documents via Salesforce.

## Endpoint: Generate Document
`POST /v1/documents/generate`

**Request Body:**
| Parameter | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| `template_id` | String | Yes | UUID of the document template. |
| `source_id` | String | Yes | Salesforce Opportunity/Account ID. |

**Example Request**
To test the endpoint, you can use the following curl command. Replace YOUR_API_KEY with your actual credential.
curl -X POST https://api.contractgen.com/v1/generate \
  -H "Content-Type: application/json" \
  -H "X-API-KEY: YOUR_API_KEY" \
  -d '{
    "template_id": "ND-001",
    "client_name": "Acme Corp",
    "effective_date": "2024-01-01",
    "provisions": ["Confidentiality", "Non-compete"]
  }'

**Example Request:**
```json
{
  "template_id": "tpl_882941",
  "source_id": "0068W000018sabc",
  "output_format": "PDF"
}

## Response Examples
###201 Created (Success)
When the request is successful, the API returns a JSON object containing the contract_id and a temporary link to the generated document.
{
  "status": "success",
  "data": {
    "contract_id": "8c59b2d1-4e2b-4f91-8874-7e102f6a627d",
    "download_url": "https://api.contractgen.com/v1/download/8c59b2d1",
    "expires_at": "2024-12-31T23:59:59Z"
  }
}
### 400 Bad Request (Error)
If required fields (such as client_name) are missing or improperly formatted, the API returns a 400 error.
{
  "status": "error",
  "message": "Validation Failed",
  "errors": [
    {
      "field": "client_name",
      "issue": "Field is required"
    }
  ]
}
