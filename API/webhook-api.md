# Webhook Subscription API

## Overview
The Webhook API allows external applications to subscribe to real-time events occurring within the Conga Sign lifecycle. Instead of polling the API for updates, your system will receive a `POST` notification the moment an event occurs.

---

## Endpoint: Create Subscription
`POST /v1/webhooks/subscriptions`

Registers a new URL to receive event notifications.

### **Request Body**
| Parameter | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| `target_url` | String | Yes | The URL where the notification will be sent. |
| `event_type` | String | Yes | Supported: `document.signed`, `document.declined`, `document.sent`. |

**Example Request:**
```json
{
  "target_url": "https://your-app.com/webhooks/conga",
  "event_type": "document.signed",
  "secret_token": "shhh_its_a_secret"
}
```

### Response Example (200 OK)
```json
{
  "subscriptions": [
    {
      "id": "sub_001",
      "target_url": "https://your-app.com/webhooks/conga",
      "status": "active",
      "created_at": "2025-12-18T12:00:00Z"
    }
  ]
}
```

### Event Payload Example
When a document is signed, your target_url will receive this JSON payload:
```json
{
  "event": "document.signed",
  "timestamp": "2025-12-18T14:30:05Z",
  "data": {
    "document_id": "doc_88291",
    "signer_email": "client@example.com",
    "audit_url": "https://congasign.com/audit/88291"
  }
}
```

---

## Security & Verification
To ensure that incoming notifications are actually from the **Contract Generator API** and not a malicious third party, we include the `secret_token` in the payload.

### **Verification Steps**
1. **Compare Tokens:** Your listener should check the `secret_token` in the incoming JSON against the token you provided during registration.
2. **Reject Unmatched Requests:** If the tokens do not match, your system should return a `401 Unauthorized` response and ignore the data.
3. **Use HTTPS:** Always use an `https://` target URL to ensure your data and tokens are encrypted during transit.

# Webhook Subscription API

## Overview
The Webhook API allows external applications to subscribe to real-time events occurring within the Conga Sign lifecycle. Instead of polling the API for updates, your system will receive a `POST` notification the moment an event occurs.

---

## Endpoint: Create Subscription
`POST /v1/webhooks/subscriptions`

Registers a new URL to receive event notifications.

### **Request Body**
| Parameter | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| `target_url` | String | Yes | The URL where the notification will be sent. |
| `event_type` | String | Yes | Supported: `document.signed`, `document.declined`, `document.sent`. |

**Example Request:**
```json
{
  "target_url": "https://your-app.com/webhooks/conga",
  "event_type": "document.signed",
  "secret_token": "shhh_its_a_secret"
}
```

### Response Example (200 OK)
```json
{
  "subscriptions": [
    {
      "id": "sub_001",
      "target_url": "https://your-app.com/webhooks/conga",
      "status": "active",
      "created_at": "2025-12-18T12:00:00Z"
    }
  ]
}
```

### Event Payload Example
When a document is signed, your target_url will receive this JSON payload:
```json
{
  "event": "document.signed",
  "timestamp": "2025-12-18T14:30:05Z",
  "data": {
    "document_id": "doc_88291",
    "signer_email": "client@example.com",
    "audit_url": "https://congasign.com/audit/88291"
  }
}
```

---

## Security & Verification
To ensure that incoming notifications are actually from the **Contract Generator API** and not a malicious third party, we include the `secret_token` in the payload.

### **Verification Steps**
1. **Compare Tokens:** Your listener should check the `secret_token` in the incoming JSON against the token you provided during registration.
2. **Reject Unmatched Requests:** If the tokens do not match, your system should return a `401 Unauthorized` response and ignore the data.
3. **Use HTTPS:** Always use an `https://` target URL to ensure your data and tokens are encrypted during transit.

---

## Status Codes

| Status Code | Meaning | Outcome |
| :--- | :--- | :--- |
| **200 OK** | **Success** | The subscription was created successfully. |
| **400 Bad Request** | **Validation Error** | The `target_url` is invalid or missing required fields. |
| **401 Unauthorized** | **Auth Error** | Your API token is invalid or expired. |
| **409 Conflict** | **Duplicate** | A subscription with this `target_url` and `event_type` already exists. |