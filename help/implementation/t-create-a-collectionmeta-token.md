---
description: Create a new Collection by creating a collectionMeta token that is passed to Livefyre.
title: Create a Collection Using the CollectionMeta Token
exl-id: d2dafc90-de21-4998-8e85-83f970524329
---
# Create a Collection Using the CollectionMeta Token{#create-a-collection-using-the-collectionmeta-token}

Create a new Collection by creating a collectionMeta token that is passed to Livefyre.

1. Create the collectionMeta token.
1. Create the checksum.

   The checksum is required if you wish to notify Livefyre of any changes that you’ve made to your Collection. Livefyre will update your Collection only if the checksum provided is different than the previously sent checksum. Creating a checksum is just like creating a `collectionMeta` token but instead of calling `buildCollectionMetaToken` you call `buildChecksum`.

Create user tokens for authenticating into Livefyre.
