---
description: Returns a Collection object instantiated as a Ratings type. Run create_or_update() from the Collection object to complete the build process.
seo-description: Returns a Collection object instantiated as a Ratings type. Run create_or_update() from the Collection object to complete the build process.
seo-title: buildRatingsCollection Site Method
title: buildRatingsCollection Site Method
uuid: 5eea2ba3-48e1-4cd2-aa73-ea81788af1df
exl-id: 84af3bb2-95f0-40e0-9a4e-830772a71862
---
# buildRatingsCollection Site Method{#buildratingscollection-site-method}

Returns a Collection object instantiated as a Ratings type. Run create_or_update() from the Collection object to complete the build process.

|Variable|Type|Description|
|--- |--- |--- |
|title|String|The title for the Collection.|
|articleId|String|A unique article ID you chose to identify a Collection within your site.|
|url|String|The canonical absolute URL for this Collection.|

## Java Example {#section_nyl_ycs_rz}

```
Collection collection = site.buildRatingsCollection(title, articleId, url); 

```

## NodeJS Example {#section_xkd_gds_rz}

```
var collection = site.buildRatingsCollection(title, articleId, url); 

```

## PHP Example {#section_ghf_gds_rz}

```
$collection = site->buildRatingsCollection(title, articleId, url); 

```

## Python Example {#section_dwg_gds_rz}

```
collection = site.build_ratings_collection(title, articleId, url) 

```

## Ruby Example {#section_enh_gds_rz}

```
collection = site.build_ratings_collection(title, articleId, url) 

```
