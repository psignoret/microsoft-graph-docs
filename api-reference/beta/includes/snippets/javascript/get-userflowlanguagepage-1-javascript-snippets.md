---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

let defaultPages = await client.api('/identity/b2cUserFlows/B2C_1_Customer/languages/en/defaultPages')
	.version('beta')
	.get();

```