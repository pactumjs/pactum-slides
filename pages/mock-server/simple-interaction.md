# Interaction

Interactions will help to simulate the HTTP requests & responses.

<v-clicks>

```js {all|1,14|3,12|4,7,8,11|4-7|8-11|all}
const { mock } = require('pactum');

mock.addInteraction({
  request: {
    method: 'GET',
    path: '/api/hello'
  },
  response: {
    status: 200,
    body: 'Hello, 👋'
  }
});

mock.start(3000);
```

</v-clicks>