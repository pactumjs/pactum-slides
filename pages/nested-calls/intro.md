# Nested Calls

Chaining multiple requests & passing data between them.

<v-clicks>

### <mdi-backburger class="inline text-red-500" /> Default

```js {0|1|2|3|all|0}
const response = await pactum.spec().get('http://jsonplaceholder.typicode.com/posts').expectStatus(200);
const id = response.json[0].id;
await pactum.spec().get(`http://jsonplaceholder.typicode.com/posts/${id}`).expectStatus(200);
```

### <mdi-arrow-left class="inline text-blue-500" /> Returns

```js {0|3|1-3|4|all|0}
const id = await pactum.spec()
                 .get('http://jsonplaceholder.typicode.com/posts')
                 .returns('[0].id');
await pactum.spec().get(`http://jsonplaceholder.typicode.com/posts/${id}`).expectStatus(200);
```

### <mdi-download class="inline text-green-500" />  Stores

```js {0|3|1-3|5|all|0}
await pactum.spec()
    .get('http://jsonplaceholder.typicode.com/posts')
    .stores('FirstPostId', '[0].id');
await pactum.spec()
    .get('http://jsonplaceholder.typicode.com/posts/$S{FirstPostId}')
    .expectStatus(200);
```

</v-clicks>