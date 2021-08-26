---
title: "Create in servicePrincipalCreationPolicy excludes"
description: "Add conditions under which a service principal creation event is excluded from a service principal creation policy."
author: "psignoret"
localization_priority: Normal
ms.prod: "identity-and-sign-in"
doc_type: apiPageType
---

# Create in servicePrincipalCreationPolicy excludes

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Add conditions under which a service principal creation event is *excluded* from a service principal creation policy. You do this by adding a [servicePrincipalCreationConditionSet](../resources/serviceprincipalcreationconditionset.md) object to the **excludes** collection of a  [servicePrincipalCreationPolicy](../resources/servicePrincipalCreationPolicy.md).

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
POST /policies/servicePrincipalCreationPolicies/{servicePrincipalCreationPolicyId}/excludes
```

## Request headers
|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|
|Content-Type|application/json. Required.|

## Request body
In the request body, supply a JSON representation of the [servicePrincipalCreationConditionSet](../resources/serviceprincipalcreationconditionset.md) object.

The following table shows the properties that are required when you create the [servicePrincipalCreationConditionSet](../resources/serviceprincipalcreationconditionset.md).

|Property|Type|Description|
|:---|:---|:---|
| id | String | The unique identifier for the service principal creation condition set. Key. Read-only. |
| applicationIds | String collection | A list of **appId** values for the applications to match with, or a list with the single value `all` to match any application. Default is the single value `all`. |
|applicationPublisherIds | String collection | A list of Microsoft Partner Network (MPN) IDs for verified publishers of the application, or a list with the single value `all` to match with applications from any publisher. Default is the single value `all`. |
| applicationsFromVerifiedPublisherOnly | Boolean | Set to `true` to only match on applications with a verified publisher. Set to `false` to match on any application, even if it does not have a verified publisher. Default is `false` |
| applicationTenantIds | String collection | A list of Azure Active Directory tenant IDs in which the application is registered, or a list with the single value `all` to match with applications registered in any tenant. Default is the single value `all`. |

## Response

If successful, this method returns a `201 Created` response code and a [servicePrincipalCreationConditionSet](../resources/serviceprincipalcreationconditionset.md) object in the response body.

## Examples

### Request

The following is an example of the request.

<!-- {
  "blockType": "request",
  "name": "create_serviceprincipalcreationconditionset_excludes"
}
-->
``` http
POST https://graph.microsoft.com/beta/policies/servicePrincipalCreationPolicies/{servicePrincipalCreationPolicyId}/excludes
Content-Type: application/json
Content-length: 277

{
  "applicationIds": [
    "52c2d821-e825-4ac9-b215-eb3ef8813fdf",
    "761c04d4-a6c3-46d9-8652-464f1a8b742e"
  ],
}
```


### Response

The following is an example of the response.

>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.servicePrincipalCreationConditionSet"
}
-->
``` http
HTTP/1.1 201 Created
Content-Type: application/json

{
    "@odata.type": "#microsoft.graph.servicePrincipalCreationConditionSet",
    "id": "5e5ba127-89d4-45e6-8188-7323d91c2776",
    "applicationIds": [
        "52c2d821-e825-4ac9-b215-eb3ef8813fdf",
        "761c04d4-a6c3-46d9-8652-464f1a8b742e"
    ],
    "applicationTenantIds": [
        "all"
    ],
    "applicationPublisherIds": [
        "all"
    ],
    "applicationsFromVerifiedPublisherOnly": false
}
```

