---
description: Track clicks back to your page from referral traffic.
title: Referral Tracking
exl-id: 9955d4a4-184d-421f-bcde-b19342b0b181
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

* [Chat](/help/using/c-about-apps/c-chat-app/c-chat-app.md) 
* [Comments](/help/using/c-about-apps/c-comments/c-comments.md) 
* [Reviews](/help/using/c-about-apps/c-reviews-app/c-reviews-app.md) 
* [Sidenotes](/help/using/c-about-apps/c-sidenotes-app/c-sidenotes-app.md)
