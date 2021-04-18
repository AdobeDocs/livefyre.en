---
description: Learn how to change from one conversation App type to another.
title: Switch Core App Types
exl-id: f18c97e8-8f39-4831-b907-afd438097e9e
---
# Switch Core App Types{#switch-core-app-types}

Learn how to change from one conversation App type to another.

Lifefyre allows you to change Collections from one Livefyre Core Application type to another (Comments, Live Blog, or Chat) by simply changing some settings in your `collectionMeta` data.

To implement a specific type of App, add a new field to your `collectionMeta` object. Comments is the default so you won’t need to make these updates if that is your desired App. To change to a different App after a Collection has been created, pass a checksum value during App initialization. Read more about creating a checksum value in our `collectionMeta` token documentation.

## Live Blog {#section_kvj_3jj_11b}

### PHP Example

```
use LivefyreLivefyre; 
  
$articleId = "1"; 
$articleTitle = "Title 1"; 
$articleURL = "https://dev.livefyre.com"; 
$articleTags = "tag1,tag2"; 
$lfType = "livecomments"; 
  
$network = Livefyre::getNetwork(networkName, networkKey); 
$site = network->getSite(siteId, siteKey); 
  
$collectionMeta = $site->buildCollectionMetaToken( 
   $articleTitle, 
   $articleURL, 
   $articleTags, 
   $lfType 
); 
  
$convConfig = array( 
   "el" => "targetElement", 
   "checksum" => $checksum, 
   "collectionMeta" => $collectionMeta, 
   "siteId" => <YOUR SITE ID>, 
   "articleId" => <ARTICLE ID> 
);
```

### Python Example

```
from livefyre import Livefyre 
  
article_id = "1" 
article_title = "Title 1" 
article_url = "https://dev.livefyre.com" 
article_tags = "tag1,tag2" 
lf_type = "livecomments" 
  
network = Livefyre.get_network(networkName, networkKey) 
site = network.get_site(siteId, siteKey) 
  
collection_meta = site.build_collection_meta_token( 
   article_title, 
   article_url, 
   article_tags, 
   lf_type, 
) 
  
conv_config = dict( 
   "el" = "targetElement", 
   "checksum" = checksum, 
   "collectionMeta" = collection_meta_token, 
   "siteId" = <YOUR SITE ID>, 
   "articleId" = <ARTICLE ID> 
)
```

### Ruby Example

```
require 'livefyre'  
article_id = "1"  
title = "Title 1"  
link = "https://dev.livefyre.com"  
tag_str = "tag1,tag2"  
lf_type = "livecomments"  
  
network = Livefyre.get_network(networkName, networkKey)  
site = network.get_site(siteId, siteKey)  
  
collection_meta = site.build_collection_meta_token( 
   title, 
   link, 
   tag_str || "", 
   lf_type, 
)  
  
conv_config = { 
   :el => targetElement, 
   :checksum => checksum, 
   :collectionMeta => collection_meta_token, 
   :siteId => <YOUR SITE ID>, 
   :articleId => <ARTICLE ID> 
}
```

## Live Blog {#section_bqt_cjj_11b}

### PHP Example

```
use LivefyreLivefyre; 
  
$articleId = "1"; 
$articleTitle = "Title 1"; 
$articleURL = "https://dev.livefyre.com"; 
$articleTags = "tag1,tag2"; 
$lfType = "liveblog"; 
  
$network = Livefyre::getNetwork(networkName, networkKey); 
$site = network->getSite(siteId, siteKey); 
  
$collectionMeta = $site->buildCollectionMetaToken( 
   $articleTitle, 
   $articleURL, 
   $articleTags, 
   $lfType 
); 
  
$convConfig = array( 
   "el" => "targetElement", 
   "checksum" => $checksum, 
   "collectionMeta" => $collectionMeta, 
   "siteId" => <YOUR SITE ID>, 
   "articleId" => <ARTICLE ID>  
);
```

### Python Example

```
from livefyre import Livefyre 
  
article_id = "1" 
article_title = "Title 1" 
article_url = "https://dev.livefyre.com" 
article_tags = "tag1,tag2" 
lf_type = "liveblog" 
  
network = Livefyre.get_network(networkName, networkKey) 
site = network.get_site(siteId, siteKey) 
  
collection_meta = site.build_collection_meta_token( 
   article_title, 
   article_url, 
   article_tags, 
   lf_type, 
) 
  
conv_config = dict( 
   "el" = "targetElement", 
   "checksum" = checksum, 
   "collectionMeta" = collection_meta_token, 
   "siteId" = <YOUR SITE ID>, 
   "articleId" = <ARTICLE ID> 
)
```

### Ruby Example

```
require 'livefyre' 
  
article_id = "1" 
title = "Title 1" 
link = "https://dev.livefyre.com" 
tag_str = "tag1,tag2" 
lf_type = "liveblog" 
  
network = Livefyre.get_network(networkName, networkKey) 
site = network.get_site(siteId, siteKey) 
  
collection_meta = site.build_collection_meta_token( 
   title, 
   link, 
   tag_str || "", 
   lf_type, 
) 
  
conv_config = { 
   :el => targetElement, 
   :checksum => checksum, 
   :collectionMeta => collection_meta_token, 
   :siteId => <YOUR SITE ID>, 
   :articleId => <ARTICLE ID> 
}
```

## Chat {#section_dqm_w3j_11b}

### PHP

```
use LivefyreLivefyre; 
  
$articleId = "1"; 
$articleTitle = "Title 1"; 
$articleURL = "https://dev.livefyre.com"; 
$articleTags = "tag1,tag2"; 
$lfType = "livechat"; 
  
$network = Livefyre::getNetwork(networkName, networkKey); 
$site = network->getSite(siteId, siteKey); 
  
$collectionMeta = $site->buildCollectionMetaToken 
   $articleTitle, 
   $articleURL, 
   $articleTags, 
   $lfType 
); 
  
$convConfig = array( 
   "el" => "targetElement", 
   "checksum" => $checksum, 
   "collectionMeta" => $collectionMeta, 
   "siteId" => <YOUR SITE ID>, 
   "articleId" => <ARTICLE ID> 
);
```

### Python Example

```
from livefyre import Livefyre 
  
article_id = "1" 
article_title = "Title 1" 
article_url = "https://dev.livefyre.com" 
article_tags = "tag1,tag2" 
lf_type = "livechat" 
  
network = Livefyre.get_network(networkName, networkKey) 
site = network.get_site(siteId, siteKey) 
  
collection_meta = site.build_collection_meta_token(  
   article_title,  
   article_url,  
   article_tags,  
   lf_type,  
)

conv_config = dict( "el" = "targetElement", 
   "checksum" = checksum, 
   "collectionMeta" = collection_meta_token, 
   "siteId" = <YOUR SITE ID>, 
   "articleId" = <ARTICLE ID> 
)
```

### Ruby Example

```
require 'livefyre' 
  
article_id = "1" 
title = "Title 1" 
link = "https://dev.livefyre.com" 
tag_str = 'tag1,tag2' 
lf_type = 'livechat' 
  
network = Livefyre.get_network(networkName, networkKey) 
site = network.get_site(siteId, siteKey) 
  
collection_meta = site.build_collection_meta_token(  
   title,  
   link, 
   tag_str || "", 
   lf_type, 
) 
  
conv_config = { 
   :el => targetElement, 
   :checksum => checksum, 
   :collectionMeta => collection_meta_token, 
   :siteId => <YOUR SITE ID>, 
   :articleId => <ARTICLE ID> 
}
```
