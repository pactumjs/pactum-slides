# Order-Service Tests

Component Tests for order-service will look like:

```js {all|1,9|11,22|3|4-7|8|14-17|18-21|all}
it('should buy a product which is in-stock', async () => {
  await pactum.spec()
    .post('http://localhost:3000/api/order-service/v1/orders')
    .withJson({
      "name": "iPhone",
      "quantity": 1
    })
    .expectStatus(200);
});

it('should not buy a product which is out-of-stock', async () => {
  await pactum.spec()
    .post('http://localhost:3000/api/order-service/v1/orders')
    .withJson({
      "name": "Galaxy",
      "quantity": 1
    })
    .expectStatus(400)
    .expectJson({
      "message": "product is out-of-stock"
    });
});
```