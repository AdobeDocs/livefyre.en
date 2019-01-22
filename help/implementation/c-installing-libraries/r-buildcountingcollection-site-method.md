---
description: Returns a Collection object instantiated as a Counting type. Run create_or_update()from the Collection object to complete the build process.
seo-description: Returns a Collection object instantiated as a Counting type. Run create_or_update()from the Collection object to complete the build process.
seo-title: buildCountingCollection Site Method
title: buildCountingCollection Site Method
uuid: e293d66a-0025-4230-997e-295ce4625713

---

# buildCountingCollection Site Method{#buildcountingcollection-site-method}

Returns a Collection object instantiated as a Counting type. Run create_or_update()from the Collection object to complete the build process.

|Variable|Type|Description|
|--- |--- |--- |
|title|String|The title for the Collection.|
|articleId|String|A unique article ID you chose to identify a Collection within your site.|
|url|String|The canonical absolute URL for this Collection.|

## Java Example {#section_nyl_ycs_rz}

```
Collection collection = site.buildCountingCollection(title, articleId, url); 

```

## NodeJS Example {#section_xkd_gds_rz}

```
var collection = site.buildCountingCollection(title, articleId, url); 

```

## PHP Example {#section_ghf_gds_rz}

```
$collection = site->buildCountingCollection(title, articleId, url); 

```

## Python Example {#section_dwg_gds_rz}

```
collection = site.build_counting_collection(title, articleId, url) 

```

## Ruby Example {#section_enh_gds_rz}

```
collection = site.build_counting_collection(title, articleId, url) 

```

