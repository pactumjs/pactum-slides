# Flows

Actual behavior is recorded as a **flow** in pactum.

```js {all|2|3-8|all}
it('get a product in-stock', async () => {
  await pactum.flow('get a product in-stock')
    .get('/api/inventory-service/v1/products')
    .withQueryParams('name', 'iPhone')
    .expectJson({
      "InStock": true
    })
    .expectStatus(200);
});
```