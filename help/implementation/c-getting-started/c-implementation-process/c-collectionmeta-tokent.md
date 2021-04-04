---
description: Create a unique token on your server that identifies every collection that you create.
seo-description: Create a unique token on your server that identifies every collection that you create.
seo-title: CollectionMeta Token
solution: Experience Manager
title: CollectionMeta Token
uuid: d5db0b0f-2807-4392-874a-94ac3c1e7550
exl-id: 52edfe75-5ce6-40c9-9afe-c34a3812f1e7
---
# CollectionMeta Token{#collectionmeta-token}

Create a unique token on your server that identifies every collection that you create.

Livefyre assigns a unique identifier to every Collection you create. Livefyre assigns a title, URL, and other parameters, including:

## collectionMeta Token Parameters

|Parameter|Type|Description|
|--- |--- |--- |
|networkName|String (optional)|The name of the Livefyre network (available from [!UICONTROL Studio] > [!UICONTROL Settings] > [!UICONTROL Integration Settings] > [!UICONTROL Credentials] ). This is optional when using the library to create a collectionMeta token.|
|networkKey|String (optional)|The secret key for the specific network (available from  Studio > Settings > Integration Settings > Credentials ). This is optional when using the library to create a collectionMeta token.|
|siteId|String (optional)|The ID for the site (available from [!UICONTROL Studio > Settings > Integration Settings > Credentials] ). Optional when using the library to create a collectionMeta token.|
|siteKey|String (optional)|The secret key for the site (available from [!UICONTROL Studio > Settings > Integration Settings > Credentials] ).|
|articleId|String (optional)|A unique ID for the Collection.|
|title|String (optional)|The title you wish to apply to the Collection. Usually, this corresponds to the title of the page that displays the App. <br>For example: “Integration is So Much Fun!” <br>Note:  The max character length for the title is 255 characters. The title field does not support HTML entities. Please encode special characters using UTF-8.|
|url|String (optional)|The canonical absolute URL you wish to attach to this Collection. This URL will be used to generate links back to the App from content shared on Facebook and Twitter, email notifications, and Livefyre Studio. <br>Note:  If testing locally, use a valid base URL domain (For example: valid: `https://customer.com`; invalid: `https://localhost:5995`).|
|tags|String (optional)|A comma-separated list of single keywords or phrases. Search Collections by tags using Studio.  </br>Note:  Tags cannot contain spaces. Use underscores if you wish a space to appear in the UI.|
|extensions|JSON (optional)|A JSON-formatted set of params to pass along to the Collection.|

## Java {#section_orz_m4n_sz}

```
import com.livefyre.Livefyre; 
import com.livefyre.core.Network; 
import com.livefyre.core.Site; 
import com.livefyre.core.Collection; 
  
Network network = Livefyre.getNetwork("networkName", "networkKey"); 
Site site = network.getSite("siteId", "siteKey"); 
Collection collection = site.buildCommentsCollection("title", "articleId", "https://www.example.com"); 
collection.getData().setTags("tags"); 
  
String collectionMetaToken = collection.buildCollectionMetaToken();

```

## NodeJS {#section_kpk_44n_sz}

```
var livefyre = require('livefyre'); 
  
var network = livefyre.getNetwork('networkName', 'networkKey'); 
var site = network.getSite('siteId', 'siteKey'); 
var collection = site.buildCommentsCollection('title', 'articleId', 'https://www.example.com'); 
collection.data.tags = 'tags'; 
  
var collectionMetaToken = collection.buildCollectionMetaToken(); 

```

## PHP {#section_zmd_zbj_tz}

```
$network = Livefyre::getNetwork("networkName", "networkKey"); 
$site = $network->getSite("siteId", "siteKey"); 
$collection = $site->buildCommentsCollection("title", "articleId", "https://www.example.com"); 
$collection->getData()->setTags("tags"); 
  
$collectionMetaToken = $collection->buildCollectionMetaToken();
```

## Python {#section_rdm_prj_tz}

```
from livefyre import Livefyre 
  
network = Livefyre.get_network('networkName', 'networkKey') 
site = network.get_site('siteId', 'siteKey') 
collection = site.build_comments_collection('title', 'articleId', 'https://www.example.com') 
collection.data.tags = 'tags' 
  
collection_meta_token = collection.build_collection_meta_token()
```

## Ruby {#section_l5n_qrj_tz}

```
require 'livefyre' 
  
network = Livefyre.get_network('networkName', 'networkKey') 
site = network.get_site('siteId', 'siteKey') 
collection = site.build_comments_collection('title', 'articleId', 'https://www.example.com') 
collection.data.tags = 'tags' 
  
collection_meta_token = collection.build_collection_meta_token 

```

>[!NOTE]
>
>Livefyre receives the collectionMeta token you build and determines uniqueness by combining siteId (Livefyre provided) and articleId (customer specified).
