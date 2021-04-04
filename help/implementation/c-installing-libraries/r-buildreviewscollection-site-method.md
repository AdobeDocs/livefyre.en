---
description: Returns a Collection object instantiated as a Reviews type. Run create_or_update() from the Collection object to complete the build process.
seo-description: Returns a Collection object instantiated as a Reviews type. Run create_or_update() from the Collection object to complete the build process.
seo-title: buildReviewsCollection Site Method
solution: Experience Manager
title: buildReviewsCollection Site Method
uuid: 88af4c68-57de-4ae9-9394-550c94ede48f
exl-id: 581ad24c-d115-4ffb-93eb-936c2da6e3fa
---
# buildReviewsCollection Site Method{#buildreviewscollection-site-method}

Returns a Collection object instantiated as a Reviews type. Run create_or_update() from the Collection object to complete the build process.

|Variable|Type|Description|
|--- |--- |--- |
|title|String|The title for the Collection.|
|articleId|String|A unique article ID you chose to identify a Collection within your site.|
|url|String|The canonical absolute URL for this Collection.|


## Java Example {#section_nyl_ycs_rz}

```
Collection collection = site.buildReviewsCollection(title, articleId, url); 

```

## NodeJS Example {#section_xkd_gds_rz}

```
var collection = site.buildReviewsCollection(title, articleId, url); 

```

## PHP Example {#section_ghf_gds_rz}

```
$collection = site->buildReviewsCollection(title, articleId, url); 

```

## Python Example {#section_dwg_gds_rz}

```
collection = site.build_reviews_collection(title, articleId, url) 

```

## Ruby Example {#section_enh_gds_rz}

```
collection = site.build_reviews_collection(title, articleId, url) 

```
