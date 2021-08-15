# Contract Testing - Pattern

Pactum is a mix of **consumer-driven** & **provider-driven** contract testing.

### Steps

<v-clicks>

1. Publish Actual Behavior (_By Provider_)
2. Publish Assumed Behavior (_From Consumer_)

</v-clicks>

<v-clicks>

```mermaid
graph LR;

    subgraph Workflow
        c[Consumer]
        p[Provider]
        pfs[Pactum Flow Server]

        p-- Publish Actual Behavior -->pfs
        c-- Publish Assumed Behavior -->pfs
        pfs-- Validate Compatibility -->pfs
    end 
```

</v-clicks>