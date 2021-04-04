---
description: Informs Livefyre to update the network’s user sync URL to the one provided. Returns a Boolean.
seo-description: Informs Livefyre to update the network’s user sync URL to the one provided. Returns a Boolean.
seo-title: setUserSyncUrl Network Method
solution: Experience Manager
title: setUserSyncUrl Network Method
uuid: cd067e90-a2da-4e3d-8e60-7eabfd86fc7f
exl-id: 8124ac0f-013f-4943-a33c-6cf8fe696f95
---
# setUserSyncUrl Network Method{#setusersyncurl-network-method}

Informs Livefyre to update the network’s user sync URL to the one provided. Returns a Boolean.

|Variable|Type|Description|
|--- |--- |--- |
|urlTemplate|String|The URL to register with Livefyre for syncing user IDs. Requires “`{id}`” to be part of the provided URL string.|

## Java Example {#section_nyl_ycs_rz}

```
network.setUserSyncUrl(urlTemplate); 
```

Sample output:

```
true
```

## NodeJS Example {#section_xkd_gds_rz}

```
network.setUserSyncUrl(urlTemplate); 

```

Sample output:

```
true
```

## PHP Example {#section_ghf_gds_rz}

```
$network->setUserSyncUrl(urlTemplate); 
```

Sample output:

```
true
```

## Python Example {#section_dwg_gds_rz}

```
network.set_user_sync_url(urlTemplate) 
```

Sample output:

```
True
```

## Ruby Example {#section_enh_gds_rz}

```
network.set_user_sync_url(urlTemplate) 
```

Sample output:

```
True
```
