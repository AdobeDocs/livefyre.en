---
description: Returns a Collection object instantiated as a Sidenotes type. Run create_or_update() from the Collection object to complete the build process.
seo-description: Returns a Collection object instantiated as a Sidenotes type. Run create_or_update() from the Collection object to complete the build process.
seo-title: buildSitenotesCollection Site Method
solution: Experience Manager
title: buildSitenotesCollection Site Method
uuid: 2bfbc032-4c0c-48d2-8ce6-02460b38bd6c
exl-id: c722baf2-91d4-4c05-97e1-ea585e91c416
---
# buildSitenotesCollection Site Method{#buildsitenotescollection-site-method}

Returns a Collection object instantiated as a Sidenotes type. Run create_or_update() from the Collection object to complete the build process.

|Variable|Type|Description|
|--- |--- |--- |
|title|String|The title for the Collection.|
|articleId|String|A unique article ID you chose to identify a Collection within your site.|
|url|String|The canonical absolute URL for this Collection.|

## Java Example {#section_nyl_ycs_rz}

```
Collection collection = site.buildSidenotesCollection(title, articleId, url); 

```

## NodeJS Example {#section_xkd_gds_rz}

```
var collection = site.buildSidenotesCollection(title, articleId, url); 

```

## PHP Example {#section_ghf_gds_rz}

```
$collection = site->buildSidenotesCollection(title, articleId, url); 

```

## Python Example {#section_dwg_gds_rz}

```
collection = site.build_sidenotes_collection(title, articleId, url) 

```

## Ruby Example {#section_enh_gds_rz}

```
collection = site.build_sidenotes_collection(title, articleId, url) 

```
