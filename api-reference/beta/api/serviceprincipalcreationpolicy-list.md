---
title: "List servicePrincipalCreationPolicies"
description: "Get a list of the servicePrincipalCreationPolicy objects and their properties."
author: "psignoret"
ms.localizationpriority: medium
ms.prod: "identity-and-sign-in"
doc_type: apiPageType
---

# List servicePrincipalCreationPolicies
Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Get a list of the [servicePrincipalCreationPolicy](../resources/serviceprincipalcreationpolicy.md) objects and their properties.

## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type|Permissions (from least to most privileged)|
|:---|:---|
| Delegated (work or school account) | Policy.Read.All, Directory.Read.All |
|Delegated (personal Microsoft account)| Not supported. |
| Application | Policy.Read.All, Directory.Read.All |

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
GET /policies/servicePrincipalCreationPolicies
```

## Optional query parameters

This method supports the `$select` [OData query parameter](/graph/query-parameters) to help customize the response. The **includes** and **excludes** navigation properties are always expanded.

## Request headers
|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|

## Request body
Do not supply a request body for this method.

## Response

If successful, this method returns a `200 OK` response code and a collection of [servicePrincipalCreationPolicy](../resources/serviceprincipalcreationpolicy.md) objects in the response body.

## Examples

### Request
<!-- {
  "blockType": "request",
  "name": "list_serviceprincipalcreationpolicy"
}
-->
``` http
GET https://graph.microsoft.com/beta/policies/servicePrincipalCreationPolicies
```


### Response

The following is an example of the response.

>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "Collection(microsoft.graph.servicePrincipalCreationPolicy)"
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
    "@odata.context": "https://graph.microsoft.com/beta/$metadata#policies/servicePrincipalCreationPolicies",
    "value": [
        {
            "id": "microsoft-verified-publishers",
            "displayName": "Verified Publishers",
            "description": "Apps from verified publishers and apps registered in this organization.",
            "isBuiltIn": true,
            "includes": [
                {
                    "id": "62ac187d-7371-4f3d-acb1-3eb856c81fae",
                    "applicationIds": [
                        "all"
                    ],
                    "applicationTenantIds": [
                        "all"
                    ],
                    "applicationPublisherIds": [
                        "all"
                    ],
                    "applicationsFromVerifiedPublisherOnly": true,
                    "certifiedApplicationsOnly": false
                },
                {
                    "id": "e5a6edd4-f07f-4cda-b192-298c12e87018",
                    "applicationIds": [
                        "all"
                    ],
                    "applicationTenantIds": [
                        "6588179e-3eb8-495f-bf5d-e802f9108689"
                    ],
                    "applicationPublisherIds": [
                        "all"
                    ],
                    "applicationsFromVerifiedPublisherOnly": true,
                    "certifiedApplicationsOnly": false
                }
            ],
            "excludes": []
        },
        {
            "id": "my-custom-sp-creation-policy",
            "displayName": "Custom service principal creation policy",
            "description": "A custom service principal creation policy to customize conditions for creating service principals.",
            "isBuiltIn": false,
            "includes": [
                {
                    "id": "ad8087b5-fef8-425c-8c92-24c32ed5bdf1",
                    "applicationIds": [
                        "all"
                    ],
                    "applicationTenantIds": [
                        "all"
                    ],
                    "applicationPublisherIds": [
                        "all"
                    ],
                    "applicationsFromVerifiedPublisherOnly": false,
                    "certifiedApplicationsOnly": false
                }
            ],
            "excludes": []
        }
    ]
}

```

