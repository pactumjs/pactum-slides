# Mock Server - Express

A mock inventory-service implemented in **express**.

```js {all|3|4-5|6-7|all}
const app = require('express')();

app.get('/api/inventory-service/v1/products', (req, res) => {
  if (req.query.name === 'iPhone') {
    res.send({ InStock = true });
  } else {
    res.send({ InStock = false });
  }
});

app.listen(4000, () => {});
```