# E2E Testing

End-To-End testing is a software testing method that validates entire software from starting to end along with its integration with external interfaces.

```js {all|3|6-8|12-14|18|all}
describe('Create a new user in system', () => {

  let e2e = pactum.e2e('Add User');

  it('create user', async () => {
    await e2e.step('Post User')
      .spec('AddUser').stores('UserID', 'id')
      .clean('DeleteUser');
  });

  it('get user', async () => {
    await e2e.step('Get User')
      .spec('GetUser')
      .expectJson({ "id": "$S{UserID}" });
  });

  it('clean up', async () => {
    await e2e.cleanup();
  });

});
```