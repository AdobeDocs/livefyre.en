---
description: Sets SSL for API calls to be on or off.
seo-description: Sets SSL for API calls to be on or off.
seo-title: setSSL Network Method
solution: Experience Manager
title: setSSL Network Method
uuid: 8d989e63-c859-456a-99ca-8d87933913ba
exl-id: 5682b84a-0b4d-479b-af40-60d2c6c38155
---
# setSSL Network Method{#setssl-network-method}

Sets SSL for API calls to be on or off.

|Variable|Type|Description|
|--- |--- |--- |
|ssl|Boolean|Default is true. if you want SSL on, false otherwise. <br><ul><li>True - SSL on </li><li>False - SSL off</li></ul>|

## Java Example {#section_nyl_ycs_rz}

```
network.setSsl(ssl); 

```

## NodeJS Example {#section_xkd_gds_rz}

```
network.ssl = false; 

```

## PHP Example {#section_ghf_gds_rz}

```
$network->setSsl(false); 

```

## Python Example {#section_dwg_gds_rz}

```
network.ssl = False 

```

## Ruby Example {#section_enh_gds_rz}

```
network.ssl = false 

```
