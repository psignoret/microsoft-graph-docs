---
title: "Update defaultUserRoleOverride"
description: "Update the properties of a defaultUserRoleOverride object."
ms.localizationpriority: medium
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

In the request body, supply the values for relevant properties that should be updated. Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values. For best performance, do not include properties that are not changing.

|Property|Type|Description|
|:---|:---|:---|
|isDefault|Boolean|Indicates whether the Microsoft default setting is in use. Set to `true` to remove overridden **rolePermissions** values and revert back to Microsoft's default setting. Set to `false` when overriding **rolePermissions* to customize [users default permissions](/azure/active-directory/fundamentals/users-default-permissions). Optional.|
|rolePermissions|[unifiedRolePermission](../resources/unifiedrolepermission.md) collection| The list of [role permissions](../resources/unifiedrolepermission.md) which indicate [users' default permissions](/azure/active-directory/fundamentals/users-default-permissions) in the organization, for the scenario identified by the **id** property. Adding, updating, or removing items from  the **rolePermissions** collection can be used to customize the default user permissions for that scenario. Optional. |
## Response

If successful, this method returns a `204 No Content` response code. It does not return anything in the response body.

## Examples

### Example 1: Disable service principal creation

By default, if a user is allowed to grant consent to the permissions requested by an application, they can trigger the creation of a service principal when they grant consent. You can disable this default behavior by removing users' permission to create service principals entirely. This will mean that user can only consent to the permissions if the application's service principal already exists, and if the user is allowed to grant the requested permissions.

#### Request

The following request overrides the default User role to remove users' default permission to create service principals.

<!-- {
  "blockType": "request",
  "name": "update_defaultuserroleoverride_disable_sp_create"
}
-->
``` http
PATCH https://graph.microsoft.com/beta/policies/authorizationPolicy/authorizationPolicy/defaultUserRoleOverrides/ServicePrincipalLimitedCreate
Content-Type: application/json

{
  "isDefault": false,
  "rolePermissions": [ ]
}
```

#### Response

<!-- {
  "blockType": "response"
}
-->
``` http
HTTP/1.1 204 No Content
```

### Example 2: Restore default setting for service principal creation

To restore the default setting for users' ability to create service principals, set **isDefault** to `true` on the `ServicePrincipalLimitedCreate` scenario.

#### Request

The following reverts the overriden role permissions for the `ServicePrincipalLimitedCreate` scenario to follow Microsoft's default settings.

<!-- {
  "blockType": "request",
  "name": "update_defaultuserroleoverride_restore_default"
}
-->
``` http
PATCH https://graph.microsoft.com/beta/policies/authorizationPolicy/authorizationPolicy/defaultUserRoleOverrides/ServicePrincipalLimitedCreate
Content-Type: application/json

{
  "isDefault": true
}
```

#### Response

<!-- {
  "blockType": "response"
}
-->
``` http
HTTP/1.1 204 No Content
```

### Example 3: Allow service principal creation with custom service principal creation policy

To control under which conditions users can create a service principal (or cause a service principal to be created, such as by granting consent to an application), override the permissions for the `ServicePrincipalLimitedCreate` scenario to include the permission to create service principals subject to a custom [service principal creation policy](../resources/servicePrincipalCreationPolicy.md).

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

{
  "isDefault": false,
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

<!-- {
  "blockType": "response"
}
-->
``` http
HTTP/1.1 204 No Content
```