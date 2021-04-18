---
description: Returns a Collection object instantiated as a Chat type. Run create_or_update() from the Collection object to complete the build process.
title: buildChatCollection Site Method
exl-id: b10f95de-9e6c-4fc3-987b-599717d5a9e7
---
# buildChatCollection Site Method{#buildchatcollection-site-method}

Returns a Collection object instantiated as a Chat type. Run create_or_update() from the Collection object to complete the build process.

|Variable|Type|Description|
|--- |--- |--- |
|title|String|The title for the Collection.|
|articleId|String|A unique article ID you chose to identify a Collection within your site.|
|url|String|The canonical absolute URL for this Collection.|

## Java Example {#section_nyl_ycs_rz}

```
Collection collection = site.buildChatCollection(title, articleId, url); 

```

## NodeJS Example {#section_xkd_gds_rz}

```
var collection = site.buildChatCollection(title, articleId, url); 

```

## PHP Example {#section_ghf_gds_rz}

```
$collection = site->buildChatCollection(title, articleId, url); 

```

## Python Example {#section_dwg_gds_rz}

```
collection = site.build_chat_collection(title, articleId, url) 

```

## Ruby Example {#section_enh_gds_rz}

```
collection = site.build_chat_collection(title, articleId, url)
```
