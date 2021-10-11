---
title: "servicePrincipalCreationPolicy resource type"
description: "Specifies the conditions under which creating a service principal can be authorized."
author: "psignoret"
ms.localizationpriority: medium
ms.prod: "identity-and-sign-in"
doc_type: resourcePageType
---

# servicePrincipalCreationPolicy resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

A service principal creation policy is used to specify the conditions under which a service principal, representing and instance of an application or a service, can be created. 

A service principal creation policy consists of a list of **includes** condition sets, and a list of **excludes** condition sets. For an event to match a service principal creation policy, it must match *at least one* of the **includes** conditions sets, and *none* of the **excludes** condition sets.

The permission to create service principals, subject to a service principal creation policy, can be included in a custom directory role.

Inherits from [policyBase](../resources/policybase.md).

## Methods
|Method|Return type|Description|
|:---|:---|:---|
|[List service principal creation policies](../api/serviceprincipalcreationpolicy-list.md) | [servicePrincipalCreationPolicy](serviceprincipalcreationpolicy.md) collection | Retrieve the list of servicePrincipalCreationPolicy objects. |
|[Create service principal creation policy](../api/serviceprincipalcreationpolicy-create.md)| [servicePrincipalCreationPolicy](serviceprincipalcreationpolicy.md) | Creates a new servicePrincipalCreationPolicy object. |
|[Get service principal creation policy](../api/serviceprincipalcreationpolicy-get.md) | [servicePrincipalCreationPolicy](serviceprincipalcreationpolicy.md) |Read properties and relationships of servicePrincipalCreationPolicy object.|
|[Update service principal creation policy](../api/serviceprincipalcreationpolicy-update.md) | [servicePrincipalCreationPolicy](serviceprincipalcreationpolicy.md)  |Update servicePrincipalCreationPolicy object. |
|**Include condition sets**| | |
|[List include condition sets](../api/serviceprincipalcreationpolicy-list-includes.md) |[servicePrincipalCreationConditionSet](serviceprincipalcreationconditionset.md) collection| Get the condition sets in the **includes** navigation property of a service principal creation policy.|
|[Add include condition set](../api/serviceprincipalcreationpolicy-post-includes.md) |[servicePrincipalCreationConditionSet](serviceprincipalcreationconditionset.md) | Add a condition set to the **includes** navigation property of a service principal creation policy. |
|[Remove include condition set](../api/serviceprincipalcreationpolicy-delete-includes.md) | None | Remove a condition set from the **includes** navigation property of a service principal creation policy.|
|**Exclude condition sets**| | |
|[List exclude condition sets](../api/serviceprincipalcreationpolicy-list-excludes.md) |[servicePrincipalCreationConditionSet](serviceprincipalcreationconditionset.md) collection| Get the condition sets in the **excludes** navigation property of a service principal creation policy.|
|[Add exclude condition set](../api/serviceprincipalcreationpolicy-post-excludes.md) |[servicePrincipalCreationConditionSet](serviceprincipalcreationconditionset.md) | Add a condition set to the **excludes** navigation property of a service principal creation policy. |
|[Remove exclude condition set](../api/serviceprincipalcreationpolicy-delete-excludes.md) | None | Remove a condition set from the **excludes** navigation property of a service principal creation policy.|

## Properties
|Property|Type|Description|
|:---|:---|:---|
| id | String | The unique identifier for the service principal creation policy. The **id** prefix `microsoft-` is reserved for built-in service principal creation policies, and may not be used in a custom service principal creation policy. Only letters, numbers, hyphens (`-`) and underscores (`_`) are allowed. Key. Not nullable. Required on create. Immutable.  Inherited from [policyBase](policyBase.md).|
| displayName | String |The display name for the service principal creation policy.  Inherited from [policyBase](policyBase.md).|
| description |String| The description for the service principal creation policy.  Inherited from [policyBase](policyBase.md).|
| isBuiltIn |Boolean|Indicates whether this is a built-in service principal creation policy. Built-in policies cannot be updated or deleted.|

## Relationships

| Relationship | Type |Description|
|:---------------|:--------|:----------|
|includes|[servicePrincipalCreationConditionSet](serviceprincipalcreationconditionset.md) collection| Condition sets which are *included* in this service principal creation policy. This navigation property is automatically expanded on **GET**. |
|excludes|[servicePrincipalCreationConditionSet](serviceprincipalcreationconditionset.md) collection| Condition sets which are *excluded* in this service principal creation policy. This navigation property is automatically expanded on **GET**. |

## JSON representation

<!-- {
  "blockType": "resource",
  "keyProperty": "id",
  "@odata.type": "microsoft.graph.servicePrincipalCreationPolicy"
}-->

```json
{
  "@odata.type": "#microsoft.graph.servicePrincipalCreationConditionSet",
  "id": "String (identifier)",
  "displayName": "String",
  "description": "String",
  "isBuiltIn": "Boolean"
}
```



