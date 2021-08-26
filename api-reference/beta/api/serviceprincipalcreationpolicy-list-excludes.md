---
title: "List servicePrincipalCreationPolicy includes"
description: "Retrieve the condition sets that describe conditions which are excluded from the service principal creation policy."
author: "psignoret"
localization_priority: Normal
ms.prod: "identity-and-sign-in"
doc_type: apiPageType
---

# List servicePrincipalCreationPolicy excludes

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Retrieve the condition sets that describe conditions which are *excluded* from the [servicePrincipalCreationPolicy](../resources/serviceprincipalcreationpolicy.md).

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
GET /policies/servicePrincipalCreationPolicies/{servicePrincipalCreationPolicyId}/excludes
```

## Optional query parameters

This method supports the `$select` [OData query parameter](/graph/query-parameters) to help customize the response.

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
GET https://graph.microsoft.com/beta/policies/servicePrincipalCreationPolicies/{servicePrincipalCreationPolicyId}/excludes
```


### Response

The following is an example of the response.

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
            "id": "5e5ba127-89d4-45e6-8188-7323d91c2776",
            "applicationIds": [
                "52c2d821-e825-4ac9-b215-eb3ef8813fdf",
                "761c04d4-a6c3-46d9-8652-464f1a8b742e"
            ],
            "applicationTenantIds": [
                "all"
            ],
            "applicationPublisherIds": [
                "all"
            ],
            "applicationsFromVerifiedPublisherOnly": false
        }
    ]
}
```

