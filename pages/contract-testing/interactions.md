# Interactions

Assumed behavior is recorded as an **interaction** in pactum.

```js {all|3,6-20|4|5|all}
it('place an order', async () => {
  await pactum.flow('place an order')
    .useInteraction({
      provider: 'inventory-service', // same as provider project
      flow: 'get a product in-stock', // same as provider flow
      request: {
        method: 'GET',
        path: '/api/inventory-service/v1/products',
        queryParams: { name: 'iPhone' }
      },
      response: {
        status: 200,
        body: { "InStock": true }
      }
    })
    .post('/api/order-service/v1/orders')
    .withJson({
      'product': 'iPhone'
    })
    .expectStatus(200);
});
```