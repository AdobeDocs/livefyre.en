---
description: Returns a new Site object.
seo-description: Returns a new Site object.
seo-title: getSite Network Method
solution: Experience Manager
title: getSite Network Method
uuid: 67de781e-5240-4be5-9e93-c614828e0bb5
index: y
internal: n
snippet: y
---

# getSite Network Method{#getsite-network-method}

Returns a new Site object.
|Variable|Type|Description|
|--- |--- |--- |
|siteId|String|The Livefyre-provided ID for the website or application to which the Collection belongs. For example: 303617.  |
|siteKey|String|The Livefyre-provided secret key for siteId.  |

## Java Example {#section_nyl_ycs_rz}

```
Site site = network.getSite(siteId, siteKey); 

```

## NodeJS Example {#section_xkd_gds_rz}

```
var site = network.getSite(siteId, siteKey); 

```

## PHP Example {#section_ghf_gds_rz}

```
$site = $network->getSite(siteId, siteKey);

```

## Python Example {#section_dwg_gds_rz}

```
site = network.get_site(siteId, siteKey) 

```

## Ruby Example {#section_enh_gds_rz}

```
site = network.get_site(siteId, siteKey) 

```

