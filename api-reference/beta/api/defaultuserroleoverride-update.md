---
title: "Update defaultUserRoleOverride"
description: "Update the properties of a defaultUserRoleOverride object."
localization_priority: Normal
author: "abhijeetsinha"
ms.prod: "identity-and-sign-in"
doc_type: "apiPageType"
---

# Update defaultUserRoleOverride

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Update the properties of a [defaultUserRoleOverride](../resources/defaultuserroleoverride.md) object.

## Permissions

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type|Permissions (from least to most privileged)|
|:---|:---|
| Delegated (work or school account)     | Policy.ReadWrite.Authorization|
| Delegated (personal Microsoft account) | Not supported. |
| Application                            | Policy.ReadWrite.Authorization|

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
PATCH /policies/authorizationPolicy/authorizationPolicy/defaultUserRoleOverrides/{defaultUserRoleOverrideId}
```

## Request headers

|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|
|Content-Type|application/json. Required.|

## Request body

In the request body, supply a JSON representation of the [defaultUserRoleOverride](../resources/defaultuserroleoverride.md) object.

## Response

If successful, this method returns a `204 No Content` response code. It does not return anything in the response body.

## Examples

### Example 1: Disable service principal creation

By default, users are allowed to cause a service principal to be created, as a result of the application consent process, if the user is allowed to grant consent to the permissions requested by the application. To disable this capability (thus, only allowing users to consent if the application's service principal already exists), override the permissions for the `ServicePrincipalLimitedCreate` scenario to remove all permissions.

#### Request

The following request overrides the default User role to disable creating service principals.

<!-- {
  "blockType": "request",
  "name": "update_defaultuserroleoverride_disable_sp_create"
}
-->
``` http
PATCH https://graph.microsoft.com/beta/policies/authorizationPolicy/authorizationPolicy/defaultUserRoleOverrides/ServicePrincipalLimitedCreate
Content-Type: application/json
Content-length: 198

{
  "isDefault": "false",
  "rolePermissions": [ ]
}
```

#### Response

>**Note:** The response object shown here might be shortened for readability.

<!-- {
  "blockType": "response"
}
-->
``` http
HTTP/1.1 204 No Content
```

### Example 2: Restore default setting for service principal creation

To restore the default setting for users' ability to create service principals, set **isDefault** to `true` on the `ServicePrincipalLimitedCreate` scenario, override the permissions for the `ServicePrincipalLimitedCreate` scenario to include the permission to create service principals subject to a custom [service principal creation policy](../resources/servicePrincipalCreationPolicy.md).

#### Request

The following request overrides the default User role to allow creating service principals only if the application meets the conditions described in the [service principal creation policy](../resources/servicePrincipalCreationPolicy.md) with **id** `my-custom-sp-creation-policy`.

<!-- {
  "blockType": "request",
  "name": "update_defaultuserroleoverride_sp_create_custom"
}
-->
``` http
PATCH https://graph.microsoft.com/beta/policies/authorizationPolicy/authorizationPolicy/defaultUserRoleOverrides/ServicePrincipalLimitedCreate
Content-Type: application/json
Content-length: 198

{
  "isDefault": "false",
  "rolePermissions": [
    {
      "allowedResourceActions": [
        "microsoft.directory/servicePrincipals/limitedCreate.my-custom-sp-creation-policy"
      ]
    }
  ]
}
```

#### Response

>**Note:** The response object shown here might be shortened for readability.

<!-- {
  "blockType": "response"
}
-->
``` http
HTTP/1.1 204 No Content
```

### Example 3: Allow service principal creation with custom service principal creation policy

To control under which conditions users can create a service principal (or cause a service principal to be created, such as by granting consent to an application) .

#### Request

The following request overrides the default User role to disable creating service principals.

<!-- {
  "blockType": "request",
  "name": "update_defaultuserroleoverride_restore_default"
}
-->
``` http
PATCH https://graph.microsoft.com/beta/policies/authorizationPolicy/authorizationPolicy/defaultUserRoleOverrides/ServicePrincipalLimitedCreate
Content-Type: application/json
Content-length: 198

{
  "isDefault": "true"
}
```

#### Response

>**Note:** The response object shown here might be shortened for readability.

<!-- {
  "blockType": "response"
}
-->
``` http
HTTP/1.1 204 No Content
```