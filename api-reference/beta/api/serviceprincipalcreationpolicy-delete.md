---
title: "Delete servicePrincipalCreationPolicy"
description: "Deletes a servicePrincipalCreationPolicy object."
author: "psignoret"
ms.localizationpriority: medium
ms.prod: "identity-and-sign-in"
doc_type: apiPageType
---

# Delete servicePrincipalCreationPolicy
Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Deletes a [servicePrincipalCreationPolicy](../resources/serviceprincipalcreationpolicy.md) object.

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
DELETE /policies/servicePrincipalCreationPolicies/{servicePrincipalCreationPolicyId}
```

## Request headers
|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|

## Request body
Do not supply a request body for this method.

## Response

If successful, this method returns a `204 No Content` response code.

## Examples

### Request
<!-- {
  "blockType": "request",
  "name": "delete_serviceprincipalcreationpolicy"
}
-->
``` http
DELETE https://graph.microsoft.com/beta/policies/servicePrincipalCreationPolicies/{servicePrincipalCreationPolicyId}
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

