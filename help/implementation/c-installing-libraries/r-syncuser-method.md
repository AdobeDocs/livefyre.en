---
description: Informs Livefyre to pull user information from a previously set user sync URL. Returns a Boolean.
seo-description: Informs Livefyre to pull user information from a previously set user sync URL. Returns a Boolean.
seo-title: syncUser Network Method
solution: Experience Manager
title: syncUser Network Method
uuid: 2affb03d-3907-4b01-9a64-02ba1b06da14
exl-id: a21ff487-2ab1-4788-b455-84941f03a98f
---
# syncUser Network Method{#syncuser-network-method}

Informs Livefyre to pull user information from a previously set user sync URL. Returns a Boolean.

|Variable|Type|Description|
|--- |--- |--- |
|userId|String|The user ID to sync with Livefyre. You must have a user sync URL set with Livefyre before calling this method.|

## Java Example {#section_nyl_ycs_rz}

```
network.syncUser(userId); 
```

Sample output:

```
true
```

## NodeJS Example {#section_xkd_gds_rz}

```
network.syncUser(userId); 
```

Sample output:

```
true
```

## PHP Example {#section_ghf_gds_rz}

```
$network->syncUser(userId); 
```

Sample output:

```
true
```

## Python Example {#section_dwg_gds_rz}

```
network.sync_user(userId) 
```

Sample output:

```
True
```

## Ruby Example {#section_enh_gds_rz}

```
network.sync_user(userId) 
```

Sample output:

```
True
```
