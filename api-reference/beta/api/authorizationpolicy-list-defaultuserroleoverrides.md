---
title: "List defaultUserRoleOverrides"
description: "Get the defaultUserRoleOverrides collection of authorizationPolicy"
author: abhijeetsinha
localization_priority: Normal
ms.prod: "identity-and-sign-in"
doc_type: apiPageType
---

# List defaultUserRoleOverrides

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Get the **defaultUserRoleOverrides** collection of the [authorizationPolicy](../resources/authorizationPolicy.md).

## Permissions

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type|Permissions (from least to most privileged)|
|:---|:---|
|Delegated (work or school account)| Policy.Read.All, Directory.Read.All, Policy.ReadWrite.Authorization |
|Delegated (personal Microsoft account)| Not supported. |
|Application| Policy.Read.All, Directory.Read.All, Policy.ReadWrite.Authorization |

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
GET /policies/authorizationPolicy/authorizationPolicyId/defaultUserRoleOverrides
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

If successful, this method returns a `200 OK` response code and a collection of [defaultUserRoleOverride](../resources/defaultuserroleoverride.md) objects in the response body.

## Examples

### Request

<!-- {
  "blockType": "request",
  "name": "list_defaultuserroleoverride"
}
-->
``` http
GET https://graph.microsoft.com/beta/policies/authorizationPolicy/authorizationPolicyId/defaultUserRoleOverrides
```

### Response

>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "Collection(microsoft.graph.defaultUserRoleOverride)"
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
    "@odata.context": "https://graph.microsoft-ppe.com/beta/$metadata#policies/authorizationPolicy('authorizationPolicy')/defaultUserRoleOverrides",
    "value": [
        {
            "id": "ServicePrincipalLimitedCreate",
            "isDefault": true,
            "rolePermissions": [
                {
                    "allowedResourceActions": [
                        "microsoft.directory/servicePrincipals/limitedCreateIfCanConsent"
                    ],
                    "condition": null
                }
            ]
        }
    ]
}
```

