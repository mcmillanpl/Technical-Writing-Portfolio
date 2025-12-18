---
layout: page
title: API Strategy - ContractGen REST API
permalink: /portfolio/api-sample/
---

# ContractGen REST API v1.0

## Overview
[cite_start]This API allows developers to programmatically generate and track legal documents via Salesforce. [cite: 65, 95]

## Endpoint: Generate Document
`POST /v1/documents/generate`

**Request Body:**
| Parameter | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| `template_id` | String | Yes | UUID of the document template. |
| `source_id` | String | Yes | [cite_start]Salesforce Opportunity/Account ID. [cite: 65] |

**Example Request:**
```json
{
  "template_id": "tpl_882941",
  "source_id": "0068W000018sabc",
  "output_format": "PDF"
}