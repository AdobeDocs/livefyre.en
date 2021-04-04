---
description: Integrate a Sidenotes app by following a process similar to Core Applications.
seo-description: Integrate a Sidenotes app by following a process similar to Core Applications.
seo-title: Sidenotes Integration
solution: Experience Manager
title: Sidenotes Integration
uuid: 4aa14ada-402a-482d-b43e-96f37afa6c53
exl-id: 368951b1-fef2-46d8-b89c-68c46962e937
---
# Sidenotes Integration{#sidenotes-integration}

Integrate a Sidenotes app by following a process similar to Core Applications.

As a general rule, if your Core Application integration is complete, the code written to generate the `collectionMeta` object may be reused for Sidenotes.

You can also reuse your existing `auth` delegates by supplying an `auth` delegate created with `fyre.conv` to Sidenotes in the (optional) `authDelegate` field.

>[!NOTE]
>
>Sidenotes allows you to include `network`, `siteId`, and `articleId` in a single object, rather than passing them separately in other parts of the constructor.

```
<!DOCTYPE html> 
<html> 
<head> 
<!-- First add Livefyre.js to the page --> 
<script src="https://cdn.livefyre.com/Livefyre.js"></script> 
</head> 
<body> 
<script type="text/javascript"> 
var convConfig = { 
 network: 'client-solutions.fyre.co', 
 selectors:'span.lyrics-sidenote', 
 siteId: '356373', 
 articleId: 'sidenotes-sample', 
 collectionMeta: 'eyJhbGciOiAiSFMyNTYiLCAidHlwIjogIkpXVCJ9.eyJ1cmwiOiAiaHR0cDovL3d3dy5zaWRlbm90ZXMtZGVtby5jb20vbHlyaWNzIiwgInNpdGVJZCI6ICIzMDQwNTkiLCAidHlwZSI6ICJzaWRlbm90ZXMiLCAiYXJ0aWNsZUlkIjogInNpZGVub3Rlc19zYW1wbGUiLCAidGl0bGUiOiAiQ2xpZW50IFNvbHV0aW9ucyBTaWRlbm90ZXMifQ.2gxnsM0TS8dfp-Jokb5uW1kuMl-DqIlqfJSCBwJgf1k' 
}; 
  
Livefyre.require(['sidenotes#1', 'auth'], function (Sidenotes, Auth) { 
 new Sidenotes(convConfig); 
 Auth.delegate({ 
 login: function (callback) { 
 callback(null,{livefyre:'<userauthtoken>'}); 
 } 
 }); 
 }); 
</script> 
</body> 
</html>
```

As noted in the Building `collectionMeta` section, `collectionMeta` is an encoded JSON object. In the example above, the JSON object takes the following format before it’s JWT encoded.

```
{ 
"title":"Client Solutions Sidenotes", 
"url":"http:\/\/www.livefyre.com\/sidenotes", 
"articleId":"sidenotes_sample", 
"siteId":"304059", 
"type":"sidenotes" 
}
```

For more information, please see the `collectionMeta` token.

## Mobile Setup

Sidenotes has been optimized for use in mobile devices. For best results with mobile versions of your Livefyre App, set the user-scalable option to no. For example:

```
<meta name="viewport" content="width=device-width, user-scalable=no">
```
