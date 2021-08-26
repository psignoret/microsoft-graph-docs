---
title: "Get servicePrincipalCreationPolicy"
description: "Read the properties and relationships of a servicePrincipalCreationPolicy object."
author: "psignoret"
localization_priority: Normal
ms.prod: "identity-and-sign-in"
doc_type: apiPageType
---

# Get servicePrincipalCreationPolicy
Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Read the properties and relationships of a [servicePrincipalCreationPolicy](../resources/serviceprincipalcreationpolicy.md) object.

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
GET /policies/servicePrincipalCreationPolicies/{servicePrincipalCreationPolicyId}
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

If successful, this method returns a `200 OK` response code and a [servicePrincipalCreationPolicy](../resources/serviceprincipalcreationpolicy.md) object in the response body.

## Examples

### Request
<!-- {
  "blockType": "request",
  "name": "get_serviceprincipalcreationpolicy"
}
-->
``` http
GET https://graph.microsoft.com/beta/policies/servicePrincipalCreationPolicies/{servicePrincipalCreationPolicyId}
```


### Response
>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.servicePrincipalCreationPolicy"
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "value": {
    "@odata.type": "#microsoft.graph.servicePrincipalCreationPolicy",
    "id": "8e53ec67-ec67-8e53-67ec-538e67ec538e",
    "deletedDateTime": "String (timestamp)",
    "description": "String",
    "displayName": "String",
    "isBuiltIn": "Boolean"
  }
}
```

