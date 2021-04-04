---
description: Returns a Collection object instantiated as a Blog type. Run create_or_update() from the Collection object to complete the build process.
seo-description: Returns a Collection object instantiated as a Blog type. Run create_or_update() from the Collection object to complete the build process.
seo-title: buildBlogCollection Site Method
solution: Experience Manager
title: buildBlogCollection Site Method
uuid: 6a5ec6b9-bc32-467a-abe6-a57c6defe067
exl-id: 93565eff-dc4e-4868-9d75-50f16ddb4fa4
---
# buildBlogCollection Site Method{#buildblogcollection-site-method}

Returns a Collection object instantiated as a Blog type. Run create_or_update() from the Collection object to complete the build process.

|Variable|Type|Description|
|--- |--- |--- |
|title|String|The title for the Collection.|
|articleId|String|A unique article ID you chose to identify a Collection within your site.|
|url|String|The canonical absolute URL for this Collection.|

## Java Example {#section_nyl_ycs_rz}

```
Collection collection = site.buildBlogCollection(title, articleId, url); 

```

## NodeJS Example {#section_xkd_gds_rz}

```
var collection = site.buildBlogCollection(title, articleId, url); 

```

## PHP Example {#section_ghf_gds_rz}

```
$collection = site->buildBlogCollection(title, articleId, url); 

```

## Python Example {#section_dwg_gds_rz}

```
collection = site.build_blog_collection(title, articleId, url) 

```

## Ruby Example {#section_enh_gds_rz}

```
collection = site.build_blog_collection(title, articleId, url) 

```
