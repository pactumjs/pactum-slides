# Simple Test

A simple test case using **PactumJS** and **mocha**.

<v-clicks>

### <mdi-flask class="inline text-green-400" /> Test Case

A test case to make a GET request to an endpoint and expect a status code.

```js {0|1|3,7|4|5|6|all}
const pactum = require('pactum');

it('should be a teapot', async () => {
  await pactum.spec()
    .get('http://httpbin.org/status/418')
    .expectStatus(418);
});
```

### <carbon-terminal class="inline text-yellow-400" /> Running Tests

Use `mocha` command to run the tests.

```shell
mocha test.js
```

</v-clicks>