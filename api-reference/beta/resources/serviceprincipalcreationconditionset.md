---
title: "servicePrincipalCreationConditionSet resource type"
description: "Specifies a matching rule with conditions under which an event is included or excluded from a service principal creation policy."
localization_priority: Normal
ms.prod: "identity-and-sign-in"
doc_type: resourcePageType
author: "psignoret"
---

# servicePrincipalCreationConditionSet resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

A service principal creation condition set is used to specify a matching rule in a [service principal creation policy](serviceprincipalcreationpolicy.md) to include or exclude a service principal creation event.

A service principal creation condition set contains several conditions. For an event to match a service principal creation condition set, all conditions must be met.

## Properties
|Property|Type|Description|
|:---|:---|:---|
| applicationIds | String collection | A list of **appId** values for the applications to match with, or a list with the single value `all` to match any application. Default is the single value `all`. Optional. |
|applicationPublisherIds | String collection | A list of Microsoft Partner Network (MPN) IDs for verified publishers of the application, or a list with the single value `all` to match with applications from any publisher. Default is the single value `all`. Optional.|
| applicationsFromVerifiedPublisherOnly | Boolean | Set to `true` to only match on applications with a verified publisher. Set to `false` to match on any application, even if it does not have a verified publisher. Default is `false`. Optional. |
| applicationTenantIds | String collection | A list of Azure Active Directory tenant IDs for the tenant where the application is registered, or a list with the single value `all` to match with applications registered in any tenant. A service principal representing an application registered in any of the tenants identified in this list will match the condition set. Default is the single value `all`. Optional. |
| id | String | The unique identifier for the service principal creation condition set. Key. Read-only. |

## JSON representation

The following is a JSON representation of the resource.
<!-- {
  "blockType": "resource",
  "keyProperty": "id",
  "@odata.type": "microsoft.graph.servicePrincipalCreationConditionSet",
  "baseType": "microsoft.graph.entity",
  "openType": false
}
-->

``` json
{
  "@odata.type": "#microsoft.graph.servicePrincipalCreationConditionSet",
  "id": "String (identifier)",
  "applicationIds": [
    "String"
  ],
  "applicationTenantIds": [
    "String"
  ],
  "applicationPublisherIds": [
    "String"
  ],
  "applicationsFromVerifiedPublisherOnly": "Boolean"
}
```

