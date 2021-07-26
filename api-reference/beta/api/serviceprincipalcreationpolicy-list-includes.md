---
title: "List includes collection of servicePrincipalCreationPolicy"
description: "Retrieve a list of the condition sets which describe conditions under which a service principal creation event is included in a service principal creation policy."
author: "psignoret"
localization_priority: Normal
ms.prod: "identity-and-sign-in"
doc_type: apiPageType
---

# List includes collection of servicePrincipalCreationPolicy

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Retrieve the condition sets which are *included* in a [servicePrincipalCreationPolicy](../resources/serviceprincipalcreationpolicy.md).

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
GET /policies/servicePrincipalCreationPolicies/{servicePrincipalCreationPolicyId}/includes
```

## Optional query parameters
This method supports some of the OData query parameters to help customize the response. For general information, see [OData query parameters](/graph/query-parameters).

## Request headers
|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|

## Request body
Do not supply a request body for this method.

## Response

If successful, this method returns a `200 OK` response code and a collection of [servicePrincipalCreationConditionSet](../resources/serviceprincipalcreationconditionset.md) objects in the response body.

## Examples

### Request
<!-- {
  "blockType": "request",
  "name": "list_serviceprincipalcreationconditionset"
}
-->
``` http
GET https://graph.microsoft.com/beta/policies/servicePrincipalCreationPolicies/{servicePrincipalCreationPolicyId}/includes
```


### Response
>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "Collection(microsoft.graph.servicePrincipalCreationConditionSet)"
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
    "value": [
        {
            "@odata.type": "#microsoft.graph.servicePrincipalCreationConditionSet",
            "id": "93b77d5e-7d5e-93b7-5e7d-b7935e7db793",
            "applicationIds": [
                "all"
            ],
            "applicationTenantIds": [
                "all"
            ],
            "applicationPublisherIds": [
                "all"
            ],
            "applicationsFromVerifiedPublisherOnly": true
        }
    ]
}
```

