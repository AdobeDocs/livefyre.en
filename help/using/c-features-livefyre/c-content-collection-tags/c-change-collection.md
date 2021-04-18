---
description: Allow users to click through Collections from a single page layout and URL.
title: Change Collection
exl-id: 5cfae2c6-e328-4d2c-b08b-709be94e4c54
---
# Change Collection{#change-collection}

Allow users to click through Collections from a single page layout and URL.

Use the Change Collection Delegate to change the Collection shown on a page, without changing the URL, while a Livefyre App is already loaded. Use this feature to display photo or video galleries, or other Apps where the displayed Collection should change after a user action.

For example, clicking a video or photo in a gallery will load a Collection specific to that selection, while the URL of the page will not change.

To load one of three Collections from a single [comment count](/help/implementation/c-advanced-topics/t-display-comment-count.md) page:

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
