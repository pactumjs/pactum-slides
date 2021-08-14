# Mock Server

Mocks services via HTTP. A simulator for HTTP based endpoints.

<v-clicks>

- 🎚 Flexible API
- 🌪️ Poweful Matchers
- 🔥 Simulate Faults
- 🎮 Remote Controlled

</v-clicks>

<v-clicks>


### Sample Mock Server

Starting a mock server.

```js
const { mock } = require('pactum');

mock.start(3000);
```

Checking health.

```shell
curl http://localhost:3000/api/pactum/health
```

</v-clicks>