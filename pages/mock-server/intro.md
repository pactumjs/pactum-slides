<!-- # Mock Server

A simulator for HTTP based endpoints.

<v-clicks>

- 🎚 Flexible API
- 🔥 Simulate Faults
- 🎮 Remote Controlled
- 🌪️ Powerful Matchers

</v-clicks> -->


# Sample Mock Server

<v-clicks>

Starting a mock server.

```js {all|1|3|all}
const { mock } = require('pactum');

mock.start(3000);
```

Checking health.

```shell
curl http://localhost:3000/api/pactum/health
```

</v-clicks>