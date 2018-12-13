---
description: Showcase multiple Collections on a single page.
seo-description: Showcase multiple Collections on a single page.
seo-title: Multiple Collections
solution: Experience Manager
title: Multiple Collections
uuid: 9675ffd7-1a59-42a1-b3ba-40af1744cfd1

---

# Multiple Collections {#multiple-collections}

Showcase multiple Collections on a single page.

You may include multiple Collections on a single page on your site. For example, to publish an event, you may have a Live Blog or Chat discussion during the event, with a separate App on the side of your page, displaying related Curated Content from around the social web. Or, you could include a Comments App below an article, with a Chat to the side.

To get multiple conversations on a page, add one or more configurations in an array and pass the array to the load call. For example.

```
<html> 
<head> 
<script src='//cdn.livefyre.com/Livefyre.js'></script> 
</head> 
<body> 
<script type="text/javascript"> 
convConfig1 = {"collectionMeta": <COLLECTION META 1>, 
             "checksum": <CHECKSUM 1>, 
             "siteId": <SITE ID>, 
             "articleId":"1", 
             "el":"livefyre"}; 
convConfig2 = {"collectionMeta": <COLLECTION META 2>, 
             "checksum": <CHECKSUM 2>, 
             "siteId": <SITE ID>, 
             "articleId":"2", 
             "el":"livefyre"}; 
convConfig3 = {"collectionMeta": <COLLECTION META 3>, 
             "checksum": <CHECKSUM 3>, 
             "siteId": <SITE ID>, 
             "articleId":"3", 
             "el":"livefyre"}; 
  
Livefyre.require(['fyre.conv#prod'],function(Conv) { 
    new Conv({"network": "<NETWORK NAME>"}, 
    [convConfig1], 
    function(app) {  
        window.changeConv = app.changeCollection; 
    } 
    ); 
}); 
</script> 
  
<div id="livefyre"></div> 
<button onclick="window.changeConv(convConfig1);">Conv 1</button> 
<button onclick="window.changeConv(convConfig2);">Conv 2</button> 
<button onclick="window.changeConv(convConfig3);">Conv 3</button> 
</body> 
</html>
```
