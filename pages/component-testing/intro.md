# Component Testing

Testing is performed on each component independently without integrating with other components.

<v-clicks>

```mermaid
graph LR;
    subgraph Controlled Environment
    t[Tests*]
    sut(Service Under Test)
    ms(Mock Server)
    db[(Database)]

    t-- 1 - Send Request -->sut
    sut-- 2 - Read/Write -->db
    sut-- 3.1 - Send Request -->ms
    ms-- 3.2 - Reply Response -->sut
    sut-- 4 - Reply Response -->t
    end
```

</v-clicks>