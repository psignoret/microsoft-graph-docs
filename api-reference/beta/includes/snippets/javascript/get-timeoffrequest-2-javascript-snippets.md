---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

let timeOffRequests = await client.api('/teams/{teamId}/schedule/timeOffRequests')
	.version('beta')
	.get();

```