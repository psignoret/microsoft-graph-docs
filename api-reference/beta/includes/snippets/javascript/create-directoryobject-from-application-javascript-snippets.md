---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

const directoryObject = {
'@odata.id': 'https://graph.microsoft.com/beta/directoryObjects/{id}'
};

await client.api('/applications/{id}/owners/$ref')
	.version('beta')
	.post(directoryObject);

```