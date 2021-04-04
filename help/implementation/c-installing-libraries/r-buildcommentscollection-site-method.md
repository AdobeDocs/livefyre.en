---
description: Returns a Collection object instantiated as a Comments type. Run createOrUpdate() from the Collection object to complete the build process.
seo-description: Returns a Collection object instantiated as a Comments type. Run createOrUpdate() from the Collection object to complete the build process.
seo-title: buildCommentsCollection Site Method
solution: Experience Manager
title: buildCommentsCollection Site Method
uuid: 0e5c062e-960d-4ab0-ba32-0965731a1571
exl-id: 9534c25a-fd1c-4a09-92e2-d196ac218ef3
---
# buildCommentsCollection Site Method{#buildcommentscollection-site-method}

Returns a Collection object instantiated as a Comments type. Run createOrUpdate() from the Collection object to complete the build process.

|Variable|Type|Description|
|--- |--- |--- |
|title|String|The title for the Collection.|
|articleId|String|A unique article ID you chose to identify a Collection within your site.|
|url|String|The canonical absolute URL for this Collection.|

## Java Example {#section_nyl_ycs_rz}

```
Collection collection = site.buildCommentsCollection(title, articleId, url);
```

## NodeJS Example {#section_xkd_gds_rz}

```
var collection = site.buildCommentsCollection(title, articleId, url); 

``` 

## PHP Example {#section_ghf_gds_rz}

```
$collection = site->buildCommentsCollection(title, articleId, url); 

```

## Python Example {#section_dwg_gds_rz}

```
collection = site.build_comments_collection(title, articleId, url) 

```

## Ruby Example {#section_enh_gds_rz}

```
collection = site.build_comments_collection(title, articleId, url) 

```
