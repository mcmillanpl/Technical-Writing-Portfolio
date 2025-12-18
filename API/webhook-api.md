---
layout: page
title: API Strategy - Webhook Notifications
---

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
  "target_url": "[https://your-app.com/webhooks/conga](https://your-app.com/webhooks/conga)",
  "event_type": "document.signed",
  "secret_token": "shhh_its_a_secret"
}
Endpoint: List Active Subscriptions
GET /v1/webhooks/subscriptions

Response Example (200 OK)
{
  "subscriptions": [
    {
      "id": "sub_001",
      "target_url": "[https://your-app.com/webhooks/conga](https://your-app.com/webhooks/conga)",
      "status": "active",
      "created_at": "2025-12-18T12:00:00Z"
    }
  ]
}
Event Payload Example
When a document is signed, your target_url will receive this JSON payload:
{
  "event": "document.signed",
  "timestamp": "2025-12-18T14:30:05Z",
  "data": {
    "document_id": "doc_88291",
    "signer_email": "client@example.com",
    "audit_url": "[https://congasign.com/audit/88291](https://congasign.com/audit/88291)"
  }
}