---
layout: center
clicks: 2
---

# Schema exposed by the Gateway

<div class="mt-2">
```graphql {all|7}
# Business Locations of PostNL
type BusinessLocation {
    locationId: ID!
    name: String
    shortName: String!
    position: Position
    assets: [Asset]
}
```
</div>