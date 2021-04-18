---
description: Some examples on using the libraries.
title: Examples
exl-id: 73b17607-0374-4037-8b0a-77e6d4b94691
---
# Examples{#examples}

Some examples on using the libraries.

## Java Example {#section_nyl_ycs_rz}

```
package com.example; 
  
import com.google.gson.JsonObject; 
import com.livefyre.Livefyre; 
import com.livefyre.core.Collection; 
import com.livefyre.core.Network; 
import com.livefyre.core.Site; 
import com.livefyre.exceptions.ApiException; 
  
public class LivefyreExample { 
  
public static void main(String...args) { 
   //build a Network class 
   Network network = Livefyre.getNetwork("`example.fyre.co`", "exampleprodbase64key"); 
  
   //update a Network's name and key 
   network.getData().setName("example-qa-fyre.co"); 
   network.getData().setKey("exampleqabase64key"); 
  
   //set SSL off 
   network.setSsl(false); 
  
   //get system and user tokens 
   String systemToken = network.buildLivefyreToken(); 
   String userToken = network.buildUserAuthToken("guest", "SuperGuest", 100000.0); 
  
   //make sure a system token is still valid 
   Boolean isValid = network.validateLivefyreToken(systemToken); 
  
   //get the network URN 
   String networkUrn = network.getUrn(); 
  
   //get the URN for a specific user 
   String userUrn = network.getUrnForUser("guest"); 
  
   //Ping for Pull (set URL then sync user afterwards) 
   network.setUserSyncUrl("www.example-qa.com/user/{id}"); 
   network.syncUser("guest"); 
  
   //get a Site class 
   Site site = network.getSite("100", "examplesite100base64key"); 
  
   //update a Site's data 
   site.getData().setId("101"); 
   site.getData().setKey("examplesite101base64key"); 
  
   //get the Site's URN 
   String siteUrn = site.getUrn(); 
  
   //build a Live Blog Collection 
   Collection blogCollection = site.buildBlogCollection("my blog!", "blog01", "www.example-qa.com/blog01"); 
   blogCollection.getData().setTags("superb"); 
   blogCollection.createOrUpdate(); 
  
   blogCollection.getData().setTags("superb, awesome"); 
   blogCollection.createOrUpdate(); 
  
   //build a Comments Collection 
   Collection commentsCollection = site.buildCommentsCollection("my comments!", "comments01", "www.example-qa.com/comments01"); 
   commentsCollection.getData().setExtensions("{\"something\":\"extra\"}"); 
   commentsCollection.createOrUpdate(); 
  
   //build a Chat Collection and retrieve content info 
   Collection chatCollection = site.buildChatCollection("my chat!", "chat01", "www.example-qa.com/chat01"); 
  
   try { 
      chatCollection.getCollectionContent(); 
   } catch (ApiException e) { 
      System.out.println("LOG: can't retrieve content of a collection that has not been created!"); 
   } 
  
   JsonObject chatCollectionData = chatCollection.createOrUpdate().getCollectionContent(); 
  
   //build a Sidenotes Collection and create checksum/token/URN 
   Collection sidenotesCollection = site.buildSidenotesCollection("my sidenotes!", "sidenotes01", "www.example-qa.com/sidenotes01"); 
   String checksum = sidenotesCollection.buildChecksum(); 
   String token = sidenotesCollection.buildCollectionMetaToken(); 
   sidenotesCollection.createOrUpdate(); 
  
   //createOrUpdate must be called to get an ID for sidenotesCollection. 
   String collectionUrn = sidenotesCollection.getUrn(); 
   } 
}
```

## NodeJS Example {#section_xkd_gds_rz}

```
var Livefyre = require('./lib/livefyre');

function LivefyreExample() { } 
module.exports = LivefyreExample; 
  
LivefyreExample.example = function example() { 
   var callback = function(error, resp) { 
      if (error) { 
         console.log('there\'s an error!'); 
      } 
   }; 
  
   //build a Network class 
   var network = Livefyre.getNetwork("`example.fyre.co`", "exampleprodbase64key"); 
  
   //update a Network's name and key 
   network.data.name = "example-qa-fyre.co"; 
   network.data.key = "exampleqabase64key"; 
  
   //set SSL off 
   network.ssl = false; 
  
   //get system and user tokens 
   var systemToken = network.buildLivefyreToken(); 
   var userToken = network.buildUserAuthToken("guest", "SuperGuest", 100000.0); 
  
   //make sure a system token is still valid 
   var isValid = network.validateLivefyreToken(systemToken); 
  
   //get the network URN 
   var networkUrn = network.getUrn(); 
  
   //get the urn for a specific user 
   var userUrn = network.getUrnForUser("guest"); 
  
   //Ping for Pull (set url then sync user afterwards) 
   network.setUserSyncUrl("www.example-qa.com/user/{id}", callback); 
   network.syncUser("guest", callback); 
  
   //get a Site class 
   var site = network.getSite("100", "examplesite100base64key"); 
  
   //update a Site's data 
   site.data.id = "101"; 
   site.data.key = "examplesite101base64key"; 
  
   //get the site's urn 
   var siteUrn = site.getUrn(); 
  
   //build a Blog collection 
   var blogCollection = site.buildBlogCollection("my blog!", "blog01", "www.example-qa.com/blog01"); 
   blogCollection.data.tags = "superb"; 
   blogCollection.createOrUpdate(function(error, collection) { 
      if (error) { 
         return; 
      } 
      collection.data.tags = "superb, awesome"; 
      collection.createOrUpdate(callback); 
   }); 
  
   //build a Comments collection 
   var commentsCollection = site.buildCommentsCollection("my comments!", "comments01", "www.example-qa.com/comments01"); 
   commentsCollection.data.extensions = "{\"something\":\"extra\"}"; 
   commentsCollection.createOrUpdate(callback); 
  
   //build a Chat collection and retrieve content info 
   var chatCollection = site.buildChatCollection("my chat!", "chat01", "www.example-qa.com/chat01"); 
  
   chatCollection.getCollectionContent(function(error, blah) { 
      if (error) { 
         console.log("LOG: can't retrieve content of a collection that has not been created!"); 
  
         chatCollection.createOrUpdate(function(error, collection) { 
            collection.getCollectionContent(callback); 
         }); 
      } 
   }); 
  
   //build a Sidenotes collection and create checksum/token/urn 
   var sidenotesCollection = site.buildSidenotesCollection("my sidenotes!", "sidenotes01", "www.example-qa.com/sidenotes01"); 
   var checksum = sidenotesCollection.buildChecksum(); 
   var token = sidenotesCollection.buildCollectionMetaToken(); 
   sidenotesCollection.createOrUpdate(callback); 
  
   //createOrUpdate must be called to get an ID for sidenotesCollection. 
   var collectionUrn = sidenotesCollection.getUrn(); 
};
```

## PHP Example {#section_ghf_gds_rz}

```
<?php 
  
namespace Example; 
  
use Livefyre\Exceptions\ApiException; 
use Livefyre\Livefyre; 
  
class LivefyreExample { 
   public function testBuildCollections() { 
      //build a Network class 
      $network = Livefyre::getNetwork("`example.fyre.co`", "exampleprodbase64key"); 
  
      //update a Network's name and key 
      $network->getData()->setName("example-qa-fyre.co"); 
      $network->getData()->setKey("exampleqabase64key"); 
  
      //set SSL off 
      $network->setSsl(false); 
  
      //get system and user tokens 
      $systemToken = $network->buildLivefyreToken(); 
      $userToken = $network->buildUserAuthToken("guest", "SuperGuest", 100000); 
  
      //make sure a system token is still valid 
      $isValid = $network->validateLivefyreToken($systemToken); 
  
      //get the $network URN 
      $networkUrn = $network->getUrn(); 
  
      //get the urn for a specific user 
      $userUrn = $network->getUrnForUser("guest"); 
  
      //Ping for Pull (set url then sync user afterwards) 
      $network->setUserSyncUrl("www.example-qa.com/user/{id}"); 
      $network->syncUser("guest"); 
  
      //get a Site class 
      $site = $network->getSite("100", "examplesite100base64key"); 
  
      //update a Site's data 
      $site->getData()->setId("101"); 
      $site->getData()->setKey("examplesite101base64key"); 
  
      //get the site's urn 
      $siteUrn = $site->getUrn(); 
  
      //build a Blog collection 
      $blogCollection = $site->buildBlogCollection("my blog!", "blog01", "www.example-qa.com/blog01"); 
      $blogCollection->getData()->setTags("superb"); 
      $blogCollection->createOrUpdate(); 
  
      $blogCollection->getData()->setTags("superb, awesome"); 
      $blogCollection->createOrUpdate(); 
  
      //build a Comments collection 
      $commentsCollection = $site->buildCommentsCollection("my comments!", "comments01", "www.example-qa.com/comments01"); 
      $commentsCollection->getData()->setExtensions("{\"something\":\"extra\"}"); 
      $commentsCollection->createOrUpdate(); 
  
      //build a Chat collection and retrieve content info 
      $chatCollection = $site->buildChatCollection("my chat!", "chat01", "www.example-qa.com/chat01"); 
  
      try { 
         $chatCollection->getCollectionContent(); 
      } catch (ApiException $e) { 
         print("LOG: can't retrieve content of a collection that has not been created!"); 
      } 
  
      $chatCollectionData = $chatCollection->createOrUpdate()->getCollectionContent(); 
  
      //build a Sidenotes collection and create checksum/token/urn 
      $sidenotesCollection = $site->buildSidenotesCollection("my sidenotes!", "sidenotes01", "www.example-qa.com/sidenotes01"); 
      $checksum = $sidenotesCollection->buildChecksum(); 
      $token = $sidenotesCollection->buildCollectionMetaToken(); 
      $sidenotesCollection->createOrUpdate(); 
  
      //createOrUpdate must be called to get an ID for sidenotesCollection. 
      $collectionUrn = $sidenotesCollection->getUrn(); 
   } 
}
```

## Python Example {#section_dwg_gds_rz}

```
from livefyre import Livefyre 
from livefyre.src.exceptions import ApiException 
  
class LivefyreExample(object): 
   def run(self): 
      #build a Network class 
      network = Livefyre.get_network('`example.fyre.co`', 'exampleprodbase64key') 
         
      #update a Network's name and key  
      network.data.name = 'example-qa-fyre.co' 
      network.data.key = 'exampleqabase64key' 
        
      #set SSL off 
       network.ssl = False 
         
      #get system and user tokens 
      system_token = network.build_livefyre_token() 
      user_token = network.build_user_auth_token('guest', 'SuperGuest', 100000) 
         
      #make sure a system token is still valid 
      is_valid = network.validate_livefyre_token(system_token) 
         
      #get the network urn 
      network_urn = network.urn 
         
      #get the urn for a specific user 
      user_urn = network.get_urn_for_user('guest') 
         
      #Ping for Pull (set url then sync user afterwards) 
      network.set_user_sync_url('www.example-qa.com/user/{id}') 
      network.sync_user('guest') 
         
      #get a Site class 
      site = network.get_site('100', 'examplesite100base64key') 
         
      #update a Site's data 
      site.data.id = '101' 
      site.data.key = 'examplesite101base64key' 
         
      #get the site's urn 
      site_urn = site.urn 
         
      #build a Blog collection 
      blog_collection = site.build_blog_collection('my blog!', 'blog01', 'www.example-qa.com/blog01') 
      blog_collection.data.tags = 'superb' 
      blog_collection.create_or_update() 
         
      blog_collection.data.tags = 'superb, awesome' 
      blog_collection.create_or_update() 
         
      #build a _comments collection 
      comments_collection = site.build_comments_collection('my comments!', 'comments01', 'www.example-qa.com/comments01') 
      comments_collection.data.extensions = '{"something":"extra"}' 
      comments_collection.create_or_update() 
         
      #build a _chat collection and retrieve content info 
      chat_collection = site.build_chat_collection('my chat!', 'chat01', 'www.example-qa.com/chat01') 
         
      try: 
         chat_collection.get_collection_content() 
      except ApiException: 
         print('LOG: can\'t retrieve content of a collection that has not been created!') 
         
      chat_collectionData = chat_collection.create_or_update().get_collection_content() 
         
      #build a Sidenotes collection and create checksum/token/urn 
      sidenotes_collection = site.build_sidenotes_collection('my sidenotes!', 'sidenotes01', 'www.example-qa.com/sidenotes01') 
      checksum = sidenotes_collection.build_checksum() 
      token = sidenotes_collection.build_collection_meta_token() 
      sidenotes_collection.create_or_update() 
         
      #create_or_update must be called to get an ID for sidenotes_collection. 
      collection_urn = sidenotes_collection.urn
```

## Ruby Example {#section_enh_gds_rz}

```
require 'livefyre' 
  
include Livefyre 
  
class LivefyreExample 
   def example 
      #build a Network class 
      network = Livefyre::get_network('`example.fyre.co`', 'exampleprodbase64key') 
         
      #update a Network's name and key  
      network.data.name = 'example-qa-fyre.co' 
      network.data.key = 'exampleqabase64key' 
         
      #set SSL off 
      network.ssl = False 
         
      #get system and user tokens 
      system_token = network.build_livefyre_token 
      user_token = network.build_user_auth_token('guest', 'SuperGuest', 100000) 
         
      #make sure a system token is still valid 
      is_valid = network.validate_livefyre_token(system_token) 
         
      #get the network urn 
      network_urn = network.urn 
         
      #get the urn for a specific user 
      user_urn = network.get_urn_for_user('guest') 
         
      #Ping for Pull (set url then sync user afterwards) 
      network.set_user_sync_url('www.example-qa.com/user/{id}') 
      network.sync_user('guest') 
         
      #get a Site class 
      site = network.get_site('100', 'examplesite100base64key') 
         
      #update a Site's data 
      site.data.id = '101' 
      site.data.key = 'examplesite101base64key' 
        
      #get the site's urn 
      site_urn = site.urn 
         
      #build a Blog collection 
      blog_collection = site.build_blog_collection('my blog!', 'blog01', 'www.example-qa.com/blog01') 
      blog_collection.data.tags = 'superb' 
      blog_collection.create_or_update 
         
      blog_collection.data.tags = 'superb, awesome' 
      blog_collection.create_or_update 
         
      #build a _comments collection 
      comments_collection = site.build_comments_collection('my comments!', 'comments01', 'www.example-qa.com/comments01') 
      comments_collection.data.extensions = '{"something":"extra"}' 
      comments_collection.create_or_update 
         
      #build a _chat collection and retrieve content info 
      chat_collection = site.build_chat_collection('my chat!', 'chat01', 'www.example-qa.com/chat01') 
         
      begin 
         chat_collection.get_collection_content 
      rescue ApiException 
         print('LOG: can\'t retrieve content of a collection that has not been created!') 
      end 
  
      chat_collectionData = chat_collection.create_or_update.get_collection_content 
         
      #build a Sidenotes collection and create checksum/token/urn 
      sidenotes_collection = site.build_sidenotes_collection('my sidenotes!', 'sidenotes01', 'www.example-qa.com/sidenotes01') 
      checksum = sidenotes_collection.build_checksum 
      token = sidenotes_collection.build_collection_meta_token 
      sidenotes_collection.create_or_update 
         
      #create_or_update must be called to get an ID for sidenotes_collection. 
      collection_urn = sidenotes_collection.urn 
   end 
end
```
