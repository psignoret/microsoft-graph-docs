---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

let subscribedSkus = await client.api('/subscribedSkus')
	.version('beta')
	.get();

```