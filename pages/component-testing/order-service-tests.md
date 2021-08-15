# Order-Service Tests

Component Tests for order-service will look like:

```js {all|1,8|10,20|3|4-6|7|13-15|16-20|all}
it('should buy a product which is in-stock', async () => {
  await pactum.spec()
    .post('http://localhost:3000/api/order-service/v1/orders')
    .withJson({
      "name": "iPhone"
    })
    .expectStatus(200);
});

it('should not buy a product which is out-of-stock', async () => {
  await pactum.spec()
    .post('http://localhost:3000/api/order-service/v1/orders')
    .withJson({
      "name": "Galaxy"
    })
    .expectStatus(400)
    .expectJson({
      "message": "product is out-of-stock"
    });
});
```