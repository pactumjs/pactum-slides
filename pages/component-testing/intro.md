# Component Testing

Testing is performed on each component independently without integrating with other components.

<v-clicks>

```mermaid
graph LR;
    subgraph Controlled Environment
    t[Tests]
    sut(Service Under Test)
    ms(Mock Server)
    db[(Database)]

    t-- Request -->sut
    sut-- Read/Write -->db
    sut-- Request -->ms
    ms-- Response -->sut
    sut-- Response -->t
    end
```

</v-clicks>