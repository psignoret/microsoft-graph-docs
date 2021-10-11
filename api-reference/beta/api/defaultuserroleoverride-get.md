---
title: "Get defaultUserRoleOverride"
description: "Read the properties and relationships of a defaultUserRoleOverride object."
author: abhijeetsinha
ms.localizationpriority: medium
ms.prod: "identity-and-sign-in"
doc_type: apiPageType
---

# Get defaultUserRoleOverride

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Read the properties and relationships of a [defaultUserRoleOverride](../resources/defaultuserroleoverride.md) object.

A **defaultUserRoleOverride** object identifies a scenario and a list of directory [role permissions](../resources/unifiedrolepermission.md) applicable to that scenario. Role permissions can be added, updated, or removed to customize [users' default permissions](/azure/active-directory/fundamentals/users-default-permissions) in an organization, for the scenario in question. A **defaultUserRoleOverride** can also be reset to follow Microsoft's default setting.

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
GET /policies/authorizationPolicy/authorizationPolicy/defaultUserRoleOverrides/{defaultUserRoleOverrideId}
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

If successful, this method returns a `200 OK` response code and a [defaultUserRoleOverride](../resources/defaultuserroleoverride.md) object in the response body.

## Examples

### Request

<!-- {
  "blockType": "request",
  "name": "get_defaultuserroleoverride"
}
-->
``` http
GET https://graph.microsoft.com/beta/policies/authorizationPolicy/authorizationPolicy/defaultUserRoleOverrides/ServicePrincipalLimitedCreate
```

### Response

The following is an example of the response. The shows the [defaultUserRoleOverride](../resources/defaultuserroleoverride.md) object for the `ServicePrincipalLimitedCreate` scenario, showing the current configuration for whether users are allowed to create service principals is following Microsoft's default settings.

>**Note:** The response object shown here might be shortened for readability.

<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.defaultUserRoleOverride"
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
    "@odata.context": "https://graph.microsoft-ppe.com/beta/$metadata#policies/authorizationPolicy('authorizationPolicy')/defaultUserRoleOverrides/$entity",
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
```

