---
title: "Create includes"
description: "Add conditions under which a service principal creation event is *included* in a service principal creation policy."
author: "psignoret"
localization_priority: Normal
ms.prod: "identity-and-sign-in"
doc_type: apiPageType
---

# Create includes

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Add conditions under which a service principal creation event is *included* in a service principal creation policy. You do this by adding a [servicePrincipalCreationConditionSet](../resources/serviceprincipalcreationconditionset.md) object to the **includes** collection of a  [servicePrincipalCreationPolicy](../resources/servicePrincipalCreationPolicy.md).

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
POST /policies/servicePrincipalCreationPolicies/{servicePrincipalCreationPolicyId}/includes
```

## Request headers
|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|
|Content-Type|application/json. Required.|

## Request body
In the request body, supply a JSON representation of the [servicePrincipalCreationConditionSet](../resources/serviceprincipalcreationconditionset.md) object. You can specify the following properties when creating a [servicePrincipalCreationConditionSet](../resources/serviceprincipalcreationconditionset.md).

|Property|Type|Description|
|:---|:---|:---|
| applicationIds | String collection | A list of **appId** values for the applications to match with, or a list with the single value `all` to match any application. Default is the single value `all`. Optional. |
|applicationPublisherIds | String collection | A list of Microsoft Partner Network (MPN) IDs for verified publishers of the application, or a list with the single value `all` to match with applications from any publisher. Default is the single value `all`. Optional. |
| applicationsFromVerifiedPublisherOnly | Boolean | Set to `true` to only match on applications with a verified publisher. Set to `false` to match on any application, even if it does not have a verified publisher. Default is `false`.  Optional.|
| applicationTenantIds | String collection | A list of Azure Active Directory tenant IDs in which the application is registered, or a list with the single value `all` to match with applications registered in any tenant. Default is the single value `all`. Optional. |
| certifiedApplicationsOnly | Boolean | Set to `true` to only match on applications that are Microsoft 365 certified. Set to `false` to match on any other client app. Default is `false`. |

## Response

If successful, this method returns a `201 Created` response code and a [servicePrincipalCreationConditionSet](../resources/serviceprincipalcreationconditionset.md) object in the response body.

## Examples

### Request

<!-- {
  "blockType": "request",
  "name": "create_serviceprincipalcreationconditionset_includes"
}
-->
``` http
POST https://graph.microsoft.com/beta/policies/servicePrincipalCreationPolicies/{servicePrincipalCreationPolicyId}/includes
Content-Type: application/json
Content-length: 277

{
  "applicationsFromVerifiedPublisherOnly": true
}
```

### Response

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
  "id": "93b77d5e-7d5e-93b7-5e7d-b7935e7db793",
  "applicationIds": [ "all" ],
  "applicationTenantIds": [ "all" ],
  "applicationPublisherIds": [ "all" ],
  "applicationsFromVerifiedPublisherOnly": true,
  "certifiedApplicationsOnly": false
}
```

