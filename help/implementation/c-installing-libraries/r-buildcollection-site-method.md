---
description: null
seo-description: null
seo-title: buildCollection Site Method
solution: Experience Manager
title: buildCollection Site Method
uuid: 52abc42a-9506-4492-b219-f2e05eb79c5f
exl-id: d5c9a2fb-2d30-44f4-8ebf-24b0ec7babee
---
# buildCollection Site Method{#buildcollection-site-method}

|Variable|Type|Description|
|--- |--- |--- |
|type|CollectionType|The type of the Collection.|
|title|String|The title for the Collection.|
|articleId|String|A unique article ID you chose to identify a Collection within your site.|
|url|String|The canonical absolute URL for this Collection.|

## Java Example {#section_nyl_ycs_rz}

```
Collection collection = site.buildCollection(type, title, articleId, url); 

```

## NodeJS Example {#section_xkd_gds_rz}

```
var collection = site.buildCollection(type, title, articleId, url); 

```

## PHP Example {#section_ghf_gds_rz}

```
$collection = site->buildCollection(type, title, articleId, url); 

```

## Python Example {#section_dwg_gds_rz}

```
collection = site.build_collection(type, title, articleId, url) 

```

## Ruby Example {#section_enh_gds_rz}

```
collection = site.build_collection(type, title, articleId, url) 

```
