---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

var securityEnabledOnly = false;

await graphClient.Contacts["{orgContact-id}"]
	.GetMemberObjects(securityEnabledOnly)
	.Request()
	.PostAsync();

```