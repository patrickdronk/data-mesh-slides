---
layout: two-cols
clicks: 4
---

# Federated GraphQL

#### BusinessLocationRegistry
```graphql {all|2}
# Business Locations of PostNL
type BusinessLocation @key(fields: "locationId") {
    locationId: ID!
    name: String
    shortName: String!
    position: Position
}
```

::right::

<div class="mt-14 ml-5">

#### AssetRegistry

```graphql {all|2-7}
# Assets
type Asset {
    assetId: ID!
    dimensions: Dimensions
}
```
<div class="mt-4">

```graphql {all|2-3|2-4}
# Enriching BusinessLocation, adding assets to it
extend type BusinessLocation @key(fields: "locationId") {
    locationId: ID! @external
    assets: [Asset]
} 
```

</div>

</div>