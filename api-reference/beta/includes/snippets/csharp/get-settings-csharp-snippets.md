---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

var settings = await graphClient.Compliance.Ediscovery.Cases["{ediscovery.case-id}"].Settings
	.Request()
	.GetAsync();

```