---
description: This method returns the URN for this network’s user.
title: getUrnForUser Network Method
exl-id: 272e724e-d09d-4d7d-9967-a229707ff47f
---
# getUrnForUser Network Method{#geturnforuser-network-method}

This method returns the URN for this network’s user.

|Variable|Type|Description|
|--- |--- |--- |
|userId|String|The userId to use in the URN.|

## Java Example {#section_nyl_ycs_rz}

```
network.getUrnForUser(userId);
```

Sample output:

```
"urn:livefyre:network=`example.fyre.co`:user=tester" 

```

## NodeJS Example {#section_xkd_gds_rz}

```
network.getUrnForUser(userId);
```

Sample output:

```
"urn:livefyre:network=`example.fyre.co`:user=tester" 

```

## PHP Example {#section_ghf_gds_rz}

```
$network->getUrnForUser(userId); 

```

Sample output:

```
"urn:livefyre:network=`example.fyre.co`:user=tester" 

```

## Python Example {#section_dwg_gds_rz}

```
network.get_urn_for_user(userId) 

```

Sample output:

```
"urn:livefyre:network=`example.fyre.co`:user=tester" 

```

## Ruby Example {#section_enh_gds_rz}

```
network.get_urn_for_user(userId) 

```

Sample output:

```
"urn:livefyre:network=`example.fyre.co`:user=tester" 

```
