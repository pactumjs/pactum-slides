# Publish Behavior

**pactum-flow-plugin** will help you to publish behavior to Pactum Flow Server.

```js {all|1,2|14-16|18-21|5|6|7|8|9|10|all}
const { reporter } = require('pactum');
const pf = require('pactum-flow-plugin');

function addFlowReporter() {
  pf.config.url = 'http://localhost:8080'; // pactum flow server url
  pf.config.projectId = 'inventory-service';
  pf.config.projectName = 'Inventory Service';
  pf.config.version = '1.0.18';
  pf.config.token = 'YWRtaW46YWRtaW4=';
  reporter.add(pf.reporter);
}

// global before
before(async () => {
  addFlowReporter();
});

// global after
after(async () => {
  await reporter.end();
});
```