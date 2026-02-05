
# Contract Generator API

## Context
**Purpose:** This API allows users to generate legal contracts dynamically by providing a template ID and specific client data.  
**Audience:** Developers and legal-tech integrators.  
**Tools Used:** Markdown, REST API Standards.

## Endpoint
`POST /v1/generate`

## Headers

| Header | Value | Description |
| :--- | :--- | :--- |
| `Content-Type` | `application/json` | Required for POST requests. |
| `X-API-KEY` | `your_api_key` | Authenticates the request. |

## Request Body
The request body must be a JSON object with the following parameters:

* `template_id` (string): The unique identifier for the contract template.
* `client_name` (string): The name of the client/entity for the contract.
* `effective_date` (string): Format `YYYY-MM-DD`.
* `provisions` (array): A list of optional clauses to include.


### **Example Request**

To test the endpoint, use the following `curl` command. Replace `YOUR_API_KEY` with your actual credential.

```bash
curl -X POST https://api.contractgen.com/v1/generate \
  -H "Content-Type: application/json" \
  -H "X-API-KEY: YOUR_API_KEY" \
  -d '{
    "template_id": "ND-001",
    "client_name": "Acme Corp",
    "effective_date": "2024-01-01",
    "provisions": ["Confidentiality", "Non-compete"]
  }'
```

## Response Examples
### **201 Created (Success)**
When the request is successful, the API returns a JSON object containing the contract_id and a temporary link to the generated document.
```JSON
{
  "status": "success",
  "data": {
    "contract_id": "8c59b2d1-4e2b-4f91-8874-7e102f6a627d",
    "download_url": "https://api.contractgen.com/v1/download/8c59b2d1",
    "expires_at": "2024-12-31T23:59:59Z"
  }
}
```

### **400 Bad Request (Error)**
If required fields (such as client_name) are missing or improperly formatted, the API returns a 400 error.
```JSON
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
```

## Status Codes (Quick Reference)
Use this guide for troubleshooting response codes:

| Status Code | Meaning | Outcome |
| :--- | :--- | :--- |
| **201 Created** | **Success!** | The contract was successfully generated and is ready for download. |
| **400 Bad Request** | **Missing Info** | The request is missing required data (like the client name) or used the wrong format. |
| **401 Unauthorized** | **Key Error** | Your API Key is missing or invalid. Check your credentials. |
| **500 Error** | **System Issue** | Something went wrong on the server side. Try again in a few minutes. |

---