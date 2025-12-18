User Access API v2.1
Overview
The User Access API allows administrators to audit and manage user permissions across the Salesforce and Conga environments. This ensures compliance with security protocols and streamlines the onboarding/offboarding process.

Endpoint: List User Permissions
Retrieves a list of all active users and their assigned Conga/Salesforce permission sets.

Request
GET /v2/access/users

Query Parameters: | Parameter | Type | Required | Description | | :--- | :--- | :--- | :--- | | status | String | No | Filter by active or inactive. | | license_type | String | No | Filter by conga_sign, conga_composer, or salesforce. |

Example Request: GET https://api.yoursystem.com/v2/access/users?status=active&license_type=conga_sign

Response
Success (200 OK)
{
  "total_results": 2,
  "users": [
    {
      "user_id": "u_9982",
      "name": "Pamela McMillan",
      "email": "mcmillan.pld@gmail.com",
      "permissions": ["Conga Sign Admin", "Salesforce User"],
      "last_login": "2025-12-18T10:30:00Z"
    },
    {
      "user_id": "u_7741",
      "name": "Jane Smith",
      "email": "jsmith@example.com",
      "permissions": ["Conga Composer User"],
      "last_login": "2025-12-15T09:15:00Z"
    }
  ]
}
Endpoint: Update User License
Assigns or removes a specific Conga license from a user.

Request
PATCH /v2/access/users/{user_id}

Example Body:
{
  "action": "assign",
  "license_name": "conga_contracts"
}
Response
Success (200 OK)
{
  "message": "License 'conga_contracts' successfully assigned to user u_9982.",
  "status": "complete"
}
