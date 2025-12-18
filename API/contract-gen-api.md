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

**Example Request:**
```json
{
  "template_id": "tpl_882941",
  "source_id": "0068W000018sabc",
  "output_format": "PDF"
}
