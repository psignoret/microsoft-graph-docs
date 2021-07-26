---
title: "Create servicePrincipalCreationPolicy"
description: "Creates a servicePrincipalCreationPolicy object that describes the conditions under which a service principal may be created."
localization_priority: Normal
doc_type: apiPageType
ms.prod: "identity-and-sign-in"
author: "psignoret"
---

# Create servicePrincipalCreationPolicy

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Creates a [servicePrincipalCreationPolicy](../resources/serviceprincipalcreationpolicy.md). A service principal creation policy is used to describe the conditions under which a service principal may be created (for example, during application consent).

After creating the service principal creation policy, you can [add include condition sets](serviceprincipalcreationpolicy-post-includes.md) to add matching rules, and [add exclude condition sets](serviceprincipalcreationpolicy-post-excludes.md) to add exclusion rules.

## Permissions

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type      | Permissions (from least to most privileged)              |
|:--------------------|:---------------------------------------------------------|
|Delegated (work or school account) | Policy.ReadWrite.ServicePrincipalCreate |
|Delegated (personal Microsoft account) | Not supported.    |
|Application | Policy.ReadWrite.ServicePrincipalCreate |

## HTTP request

<!-- { "blockType": "ignored" } -->
```http
POST /policies/servicePrincipalCreationPolicies
```

## Request headers

| Name       | Description|
|:-----------|:----------|
| Authorization | Bearer {token}. Required.  |
| Content-type | application/json. Required. |

## Request body
In the request body, supply a JSON representation of the [servicePrincipalCreationPolicy](../resources/serviceprincipalcreationpolicy.md) object.

## Response

If successful, this method returns a `201 Created` response code and a [servicePrincipalCreationPolicy](../resources/serviceprincipalcreationpolicy.md) object in the response body.

## Examples

### Request
<!-- {
  "blockType": "request",
  "truncated": true,
  "name": "create_serviceprincipalcreationpolicy"
}-->

```http
POST https://graph.microsoft.com/beta/policies/servicePrincipalCreationPolicies
Content-Type: application/json

{
  "id": "my-custom-sp-create-policy",
  "displayName": "Custom service principal creation policy",
  "description": "A custom service principal creation policy to customize conditions for creating service principals."
}
```


### Response
>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.servicePrincipalCreationPolicy"
} -->

```http
HTTP/1.1 200 OK
Content-type: application/json

{
  "id": "my-custom-sp-create-policy",
  "displayName": "Custom service principal creation policy",
  "description": "A custom service principal creation policy to customize conditions for creating service principals."
}
```

