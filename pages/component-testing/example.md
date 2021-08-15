# Component Testing - Example

Assume an e-commerce application that is built on micro-services architecture.

<v-clicks>

```mermaid
graph LR;
    u[User]

    subgraph E-Commerce Infra
    os(Order Service)
    is(Inventory Service)

    os-- Check Inventory -->is
    end

    u-- Place an Order -->os
```

### Endpoints

- **POST** - /api/order-service/v1/orders

- **GET** - /api/inventory-service/v1/products

</v-clicks>