# Component Test - Pactum

Pactum uses a method called `useInteraction` to add behavior to the mock server.

```js {all|2,14-19|3-13|4-8|9-12|all}
it('should buy a product which is in-stock', async () => {
  await pactum.spec()
    .useInteraction({
      request: {
        method: 'GET',
        path: '/api/inventory-service/v1/products',
        queryParams: { product: 'iPhone' }
      },
      response: {
        status: 200,
        body: { "InStock": true }
      }
    })
    .post('http://localhost:3000/api/order-service/v1/orders')
    .withJson({
      "name": "iPhone",
      "quantity": 1
    })
    .expectStatus(200);
});
```