---
title: "Delete from servicePrincipalCreationPolicy excludes"
description: "Deletes an excluded condition set from service principal creation policy."
localization_priority: Normal
doc_type: apiPageType
ms.prod: "identity-and-sign-in"
author: "psignoret"
---

# Delete from servicePrincipalCreationPolicy excludes

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Deletes a [condition set](../resources/serviceprincipalcreationconditionset.md) from the **excludes** collection of a [servicePrincipalCreationPolicy](../resources/serviceprincipalcreationpolicy.md).


## Permissions

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

| Permission type      | Permissions (from least to most privileged)              |
|:--------------------|:---------------------------------------------------------|
| Delegated (work or school account) | Policy.ReadWrite.ServicePrincipalCreate |
| Delegated (personal Microsoft account) | Not supported.    |
| Application | Policy.ReadWrite.ServicePrincipalCreate |

## HTTP request

<!-- { "blockType": "ignored" } -->

```http
DELETE /policies/servicePrincipalCreationPolicies/{serviceprincipalcreationpolicy-id}/excludes/{exclude-id}
```

## Request headers

| Name       | Type | Description|
|:---------------|:--------|:----------|
| Authorization  | string  | Bearer {token}. Required. |

## Request body

Do not supply a request body for this method.

## Response

If successful, this method returns a `204 No Content` response code. It does not return anything in the response body.

## Examples

### Request

The following is an example of the request.

<!-- {
  "blockType": "request",
  "name": "serviceprincipalcreationpolicy_delete_excludes"
}-->

```http
DELETE https://graph.microsoft.com/beta/policies/servicePrincipalCreationPolicies/my-custom-sp-creation-policy/excludes/6a846635-3e70-4a10-821e-512a0db93cbd
```

### Response

The following is an example of the response.

<!-- {
  "blockType": "response",
  "truncated": true
} -->

```http
HTTP/1.1 204 No Content
```

