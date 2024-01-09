# Create a pull request
A pull request is an event used in version control systems, such as Git, to propose changes made in the branch of a repository for review and merging into another branch. A pull request allows collaborators to review and discuss the proposed changes, suggest modifications, and approve the changes into the target branch. 

## Prerequisites 
Before you can send an API query, you will require:
- PLM Apps account profile.
- API access token to authenticate requests.
- Postman account.

## Retrieve a pull request
`GET https://dev.plmapps.com/{company}/{name}/_apis/plm/repositories/{repositoryId}/pullrequests/{pullRequestId}`

## Parameters
| Name | Required | Type | Description |
| ----------- | ----------- | ----------- | ----------- |
| `company` | True | String | The name of the company. |
| `pullRequestId` | Integer | String | The ID of the pull request. |
| `repositoryId` | True | String | The ID of the repository of the target branch. |
| `name` | False | String | Project name/ID. |
| `version` | True | Query | Version of the API to use. |
| `body` | False | String | Description for the pull request. |
| `head` | True | String | The name of the branch where changes are implemented. |
| `base` | True | String | The name of the branch where changes will be pulled into. |

## Request body
| Name | Required | Type | Description |
| ----------- | ----------- | ----------- | ----------- |
| `commits` | True | String | The commits included in the request. |
| `description` | True | String | The description of the request. |
| `mergeID` | True | String | The ID of the job running the pull request. |
| `status` | True | String | Status of the pull request. |
| `title` | True | String | Title of the pull request. |

## Response
| Name | Required | Type | Description |
| ----------- | ----------- | ----------- | ----------- |
| `300 AP` | True | string | Successful pull request |
| `401 EX` | True | string | Failed pull request |

## Samples
### Request
HTTP

```
POST https://dev.plmapps.com/_apis/plm/repositories/333.13.321/pullrequests?api-version=3.1
{
   "company": "PLM Company Ex",
   "pullRequestId": "333456",
   "repositoryId": "12345",
   "name": "Sample Tech Writing",
   "version": "0k-123"
   "body": "Creating a sample of tech writing",
   "head": "mcm-988-tch-wrtng",
   "base": "Dev1",
}
```

### Response
Status code: 301

JSON

```
{
   "repository": {
    "id": "333456",
    "name": "Sample Tech Writing",
 "url": "https://dev.plmapps.com/_apis/plm/repositories/333.13.321/pullrequests?api-version=3.1",
   "project": {
    "commits": "xya-3330345",
    "description": "2016_10_31",
    "mergeId": "Creating a sample of tech writing",
    "status": "300 AP",
    "title": "Sample Tech",
    "revision": 3
   }
  }
}
```
