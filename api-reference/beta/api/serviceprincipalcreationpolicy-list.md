---
title: "List servicePrincipalCreationPolicies"
description: "Get a list of the servicePrincipalCreationPolicy objects and their properties."
author: "psignoret"
localization_priority: Normal
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
  "value": [
    {
      "@odata.type": "#microsoft.graph.servicePrincipalCreationPolicy",
      "id": "8e53ec67-ec67-8e53-67ec-538e67ec538e",
      "deletedDateTime": "String (timestamp)",
      "description": "String",
      "displayName": "String",
      "isBuiltIn": "Boolean"
    }
  ]
}
```

