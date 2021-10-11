---
title: "defaultUserRoleOverride resource type"
description: "Overriden permissions of the default Users directory role definition."
ms.localizationpriority: medium
author: "abhijeetsinha"
ms.prod: "identity-and-sign-in"
doc_type: "resourcePageType"
---

# defaultUserRoleOverride resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

A **defaultUserRoleOverride** objects allows some [default user permissions](/azure/active-directory/fundamentals/users-default-permissions) to be overridden. Each **defaultUserRoleOverride** object identifies a scenario and a list of directory [role permissions](../resources/unifiedrolepermission.md) applicable to that scenario. Role permissions can be added, updated, or removed to customize the default user permissions in an organization, for the scenario in question. A **defaultUserRoleOverride** can also be reset to Microsoft's default behavior configuration.

## Methods

|Method|Return type|Description|
|:---|:---|:---|
|[List defaultUserRoleOverrides](../api/authorizationpolicy-list-defaultuserroleoverrides.md)|[defaultUserRoleOverride](../resources/defaultuserroleoverride.md) collection| Retrieve a collection of [defaultUserRoleOverride](../resources/defaultuserroleoverride.md) objects and their properties.|
|[Get defaultUserRoleOverride](../api/defaultuserroleoverride-get.md)|[defaultUserRoleOverride](../resources/defaultuserroleoverride.md)|Read the properties and relationships of a [defaultUserRoleOverride](../resources/defaultuserroleoverride.md) object.|
|[Update defaultUserRoleOverride](../api/defaultuserroleoverride-update.md)|[defaultUserRoleOverride](../resources/defaultuserroleoverride.md)|Update the properties of a [defaultUserRoleOverride](../resources/defaultuserroleoverride.md) object.|

## Properties

|Property|Type|Description|
|:---|:---|:---|
|id|String|The scenario identifier for this [defaultUserRoleOverride](../resources/defaultuserroleoverride.md). Allowed values: <ul><li>`ServicePrincipalLimitedCreate`: The limited permissions to create a [servicePrincipal](serviceprincipal.md) object, subject to a [servicePrincipalCreationPolicy](serviceprincipalcreationpolicy.md).</li></ul>|
|isDefault|Boolean|Indicates whether the Microsoft default setting is in use. Set to `true` to remove overridden **rolePermissions** values and revert back to Microsoft's default setting. Set to `false` when overriding **rolePermissions* to customize [users' default permissions](/azure/active-directory/fundamentals/users-default-permissions).|
|rolePermissions|[unifiedRolePermission](../resources/unifiedrolepermission.md) collection| The list of [role permissions](../resources/unifiedrolepermission.md) which indicate [users' default permissions](/azure/active-directory/fundamentals/users-default-permissions) in the organization, for the scenario identified by the **id** property. Adding, updating or removing items from  the **rolePermissions** collection can be used to customize the default user permissions for that scenario. |

## Relationships

None.

## JSON representation

The following is a JSON representation of the resource.
<!-- {
  "blockType": "resource",
  "keyProperty": "id",
  "@odata.type": "microsoft.graph.defaultUserRoleOverride",
  "baseType": "microsoft.graph.entity",
  "openType": false
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.defaultUserRoleOverride",
  "id": "String (identifier)",
  "isDefault": "Boolean",
  "rolePermissions": [
    {
      "@odata.type": "microsoft.graph.unifiedRolePermission"
    }
  ]
}
```

