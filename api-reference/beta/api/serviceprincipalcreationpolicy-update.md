---
title: "Update servicePrincipalCreationPolicy"
description: "Update the properties of a servicePrincipalCreationPolicy object."
author: "psignoret"
localization_priority: Normal
ms.prod: "identity-and-sign-in"
doc_type: apiPageType
---

# Update servicePrincipalCreationPolicy
Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Update the properties of a [servicePrincipalCreationPolicy](../resources/serviceprincipalcreationpolicy.md) object.

## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type|Permissions (from least to most privileged)|
|:---|:---|
| Delegated (work or school account) | Policy.ReadWrite.ServicePrincipalCreate |
|Delegated (personal Microsoft account)| Not supported. |
| Application | Policy.ReadWrite.ServicePrincipalCreate |

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
PATCH /policies/servicePrincipalCreationPolicies/{servicePrincipalCreationPolicyId}
```

## Request headers
|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|
|Content-Type|application/json. Required.|

## Request body
In the request body, supply a JSON representation of the [servicePrincipalCreationPolicy](../resources/serviceprincipalcreationpolicy.md) object.

In the request body, supply the values for relevant properties that should be updated. Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values. For best performance, do not include properties that are not changing.

|Property|Type|Description|
|:---|:---|:---|
| displayName | String |The display name for the service principal creation policy.|
| description |String| The description for the service principal creation policy.|

## Response

If successful, this method returns a `200 OK` response code and an updated [servicePrincipalCreationPolicy](../resources/serviceprincipalcreationpolicy.md) object in the response body.

## Examples

### Request

<!-- {
  "blockType": "request",
  "name": "update_serviceprincipalcreationpolicy"
}
-->
``` http
PATCH https://graph.microsoft.com/beta/policies/servicePrincipalCreationPolicies/{servicePrincipalCreationPolicyId}
Content-Type: application/json
Content-length: 199

{
  "displayName": "My service principal creation policy",
  "description": "This is a custom service principal creation policy to customize conditions for creating service principals."
}
```

### Response

<!-- {
  "blockType": "response",
  "truncated": true
}
-->
``` http
HTTP/1.1 204 No Content
```

