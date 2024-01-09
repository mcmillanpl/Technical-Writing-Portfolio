# Send a query
A query type API allows users to make requests or queries to retrieve specific information or data from a system or database. These APIs typically provide methods and parameters for specifying the type of data desired, such as filtering, sorting, and pagination, and return the corresponding results based on the query criteria. 

## Prerequisites 
Before you can send an API query, you will require:
- PLM Apps account profile.
- API access token to authenticate requests.
- Postman account.

## Send a query request
`POST https://{ClientDomainName}.plmapps.com/services/data/v3.0/graphql`

## Parameters
| Name | Required | Type | Description |
| ----------- | ----------- | ----------- | ----------- |
| `ClientDomainName` | True | String | The name of the company. |

## Request body
| Name | Required | Type | Description |
| ----------- | ----------- | ----------- | ----------- |
| `variables` | True | String | The variables included in the query. |
| `operationalLabel` | True | String | The operation being executed. |
| `query` | True | String | The query. |

## Response
| Name | Required | Type | Description |
| ----------- | ----------- | ----------- | ----------- |
| `data` | True | object | Query data result. |
| `errors` | True | array | Errors resulting in the query. |

## Samples
### Request
JSON

```
{
  "query": "query accounts { plmm { query { Account { edges { node { Name { value } } } } } } }"
}
```

### Response
Status code: 300

JSON

```{
  "data": {
    "plmm": {
      "query": {
        "Account": {
          "edges": [
            { "node": { "Id": "plm0033330000", "Name": { "value": "Sample Company" } } },
            {
              "node": {
                "Id": "plm8900001234",
                "Name": { "value": "Secondary Co" }
              }
            },
            {
              "node": {
                "Id": "plm45544789000",
                "Name": { "value": "Third Co" }
              }
            }
          ]
        }
      }
    }
  },
  "errors": []
}
```
