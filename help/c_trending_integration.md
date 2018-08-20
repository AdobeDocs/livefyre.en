---
description: Showcase the most active Collections on your Site or Network.
seo-description: Showcase the most active Collections on your Site or Network.
seo-title: Trending
solution: Experience Manager
title: Trending
uuid: 5d9f7085-7f35-4ad5-a2b0-f17500e83a76
index: y
internal: n
snippet: y
translate: y
---

# Trending

Use Trending to showcase the Collections with the most recent activity in your Site or Network. 

## Integration {#section_wtz_whb_c1b}

The quickest way to integrate with Trending is to use the built version hosted on Livefyre’s CDN. 

First, add [ Livefyre.js ](https://github.com/Livefyre/Livefyre.js) to your page. 

```
<script src="//cdn.livefyre.com/Livefyre.js"></script> 

```
Then, position the element in which the App will appear. 

```
<div id="trending"></div>
```
Finally, use ` Livefyre.require` to construct the component. 

```
<script> 
Livefyre.require([ 
   'streamhub-hot-collections#0' 
], function(Trending) {     
   var app = new Trending({ 
      el: document.getElementById("trending"), 
      network: 'livefyre.com' 
   }); 
   app.start(); 
}); 
</script>
```
You now have a Trending App! See this all in action in [ this example ](http://codepen.io/gobengo/pen/GijEy). 

## Configuration {#section_k5k_qhb_c1b}

` network` 

The Network from which Collections will be pulled. (Required.) 

```
var trending = new Trending({ 
   el: document.getElementById('trending'), 
   network: 'livefyre.com' 
});
```
` siteId` 

Provide the Site ID to show Collections only from a single Site within your Network. (Optional.) 

```
var trending = new Trending({ 
   el: document.getElementById('trending'), 
   network: 'livefyre.com', 
   siteId: 4 
});
```
` tag` 

Provide a single Collection tag to show only Collections with that tag. (Optional.) 

```
var trending = new Trending({ 
   el: document.getElementById('trending'), 
   network: 'livefyre.com', 
   siteId: 4, 
   tag: 'basketball' 
});
```
