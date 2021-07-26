---
title: "defaultUserRoleOverride resource type"
description: "Overriden permissions of the default Users directory role definition."
localization_priority: Normal
author: "abhijeetsinha"
ms.prod: "identity-and-sign-in"
doc_type: "resourcePageType"
---

# defaultUserRoleOverride resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Overriden permissions of the default Users directory role definition.

Inherits from [entity](../resources/entity.md).

## Methods

|Method|Return type|Description|
|:---|:---|:---|
|[List defaultUserRoleOverrides](../api/authorizationpolicy-list-defaultuserroleoverrides.md)|[defaultUserRoleOverride](../resources/defaultuserroleoverride.md) collection|Get the list of [defaultUserRoleOverride](../resources/defaultuserroleoverride.md) entries and their properties.|
|[Get defaultUserRoleOverride](../api/defaultuserroleoverride-get.md)|[defaultUserRoleOverride](../resources/defaultuserroleoverride.md)|Read the properties and relationships of a [defaultUserRoleOverride](../resources/defaultuserroleoverride.md) entry.|
|[Update defaultUserRoleOverride](../api/defaultuserroleoverride-update.md)|[defaultUserRoleOverride](../resources/defaultuserroleoverride.md)|Update the properties of a [defaultUserRoleOverride](../resources/defaultuserroleoverride.md) entry.|

## Properties

|Property|Type|Description|
|:---|:---|:---|
|id|String|The scenario identifier for this [defaultUserRoleOverride](../resources/defaultuserroleoverride.md). Allowed values: <ul><li>`ServicePrincipalLimitedCreate`: The limited permissions to create a [servicePrincipal](serviceprincipal.md) object, subject to a [servicePrincipalCreationPolicy](serviceprincipalcreationpolicy.md).</li></ul>|
|isDefault|Boolean|Indicates whether the Microsoft default setting is in use. Set to `true` to revert back to Microsoft's default setting.|
|rolePermissions|[unifiedRolePermission](../resources/unifiedrolepermission.md) collection| The list of role permissions which are considered to be a part of the default Users directory [role definition](../resources/unifiedroledefinition.md). |

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

