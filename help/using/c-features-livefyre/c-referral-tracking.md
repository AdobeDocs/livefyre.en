---
description: Track clicks back to your page from referral traffic.
seo-description: Track clicks back to your page from referral traffic.
seo-title: Referral Tracking
solution: Experience Manager
title: Referral Tracking
uuid: 7daf615d-0c07-49d1-adb2-1ac67ea563e7
exl-id: 44cc221c-1603-4e6e-ae4a-1b993f7dc446
---
# Referral Tracking{#referral-tracking}

Track clicks back to your page from referral traffic.

Livefyre appends a referral variable to the URL when a comment is posted or shared to a social network, and for permalinks included in Livefyre emails. Use this variable to track referral traffic from Livefyre Apps to your social or owned properties.

Livefyre Apps allow you to track data streams resulting from referral traffic, allowing you to analyze your site’s traffic.

## Tracking Livefyre Referral Traffic {#section_nsy_qp4_xz}

Livefyre referral traffic from social networks and emails may be tracked by inspecting the query string parameters in the URLs of your pages and implementing code on your page to track this through your analytics provider. Livefyre appends a referral link to the URL when a comment is posted or shared to a social network, and for permalinks included in Livefyre emails.

## Implementation Example {#section_xvs_x44_xz}

If the traffic was from a StreamHub-powered notification, there will be a hubRefSrc query string parameter with a value of email, facebook, twitter, linkedin, or permalink. The hubRefSrc parameter name can be configured at the network level by your Livefyre delivery team.

To integrate with an analytics platform, your page must look for the hubRefSrc on load, and record the traffic if it is present.

For example:

```
(function () { 
   var qs = document.location.search.substring(1), 
      param = 'hubRefSrc', 
      valueRegex = new RegExp(param+'=([^&]+)'), 
      match = qs.match(valueRegex), 
      referrer; 
   if (match) { 
      // StreamHub generated traffic! 
      referrer = match[1]; 
      console.log('StreamHub referred via', referrer); 
   } else { 
      // StreamHub did not refer this traffic 
   } 
}())
```



Apps that use this feature:

* [Chat](../c-about-apps/c-chat-app/c-chat-app.md#c_chat_app) 
* [Comments](/help/using/c-about-apps/c-comments/c-comments.md) 
* [Reviews](../c-about-apps/c-reviews-app/c-reviews-app.md#c_reviews_app) 
* [Sidenotes](../c-about-apps/c-sidenotes-app/c-sidenotes-app.md#c_sidenotes_app)
