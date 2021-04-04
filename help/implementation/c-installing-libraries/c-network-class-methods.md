---
description: Create a Network object.
seo-description: Create a Network object.
seo-title: Network Class Methods
solution: Experience Manager
title: Network Class Methods
uuid: 4130beda-dd09-49ae-aafb-f6b956e30b51
exl-id: 5a011120-05d0-4768-9038-6a312e8c5dd1
---
# Network Class Methods{#network-class-methods}

Create a Network object.

Once you create a network object, the rest of the page will assume that you have a instantiated Network object in your session.

## Network Object

|  Parameter  | Type  | Description  |
|---|---|---|
|  *`network`* | String  | Your Livefyre network. For example: “`labs.fyre.co`”.  |
|  *`networkKey`* | String  | The Livefyre-provided secret key for the network.  |

## Java {#section_myk_dzs_kbb}

```
import com.livefyre.Livefyre; 
  
Network network = Livefyre.getNetwork(network, networkKey); 
```

## NodeJS {#section_nyk_dzs_kbb}

```
var livefyre = require('livefyre'); 
  
var network = livefyre.getNetwork(network, networkKey); 
```

## PHP {#section_oyk_dzs_kbb}

```
use Livefyre\Livefyre; 
  
$network = Livefyre::getNetwork(network, networkKey); 
```

## Python {#section_pyk_dzs_kbb}

```
from livefyre import Livefyre 
  
network = Livefyre.get_network(network, networkKey) 
```

## Ruby {#section_qyk_dzs_kbb}

```
require 'livefyre' 
  
network = Livefyre.get_network(network, networkKey) 
```
