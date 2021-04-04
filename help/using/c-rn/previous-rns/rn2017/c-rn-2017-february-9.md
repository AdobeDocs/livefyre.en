---
description: Release Notes for the February 9, 2017 release.
seo-description: Release Notes for the February 9, 2017 release.
seo-title: February 9, 2017
title: February 9, 2017
uuid: cbbf10f3-d8ca-4c10-849e-fa7208f987be
exl-id: 155f8a43-17e5-40b2-ada0-32691f8a34e5
---
# February 9, 2017{#february}

Release Notes for the February 9, 2017 release.

## SocialSync for Twitter {#section_nv4_yry_wy}

SocialSync for Twitter has been a part of our core functionality for several years. However, as our product has developed and grown over time, SocialSync for Twitter has become a lower-value feature that is currently used by a very small portion of our customer base. To improve the overall experience of Livefyre for our customers and focus development resources in areas of greatest value, we will be discontinuing the SocialSync for Twitter feature on February 24. SocialSync for Facebook will be unaffected by this update. If you have any questions or concerns about this update, please reach out to your Livefyre CSM.

## Production Release {#section_r24_1m2_wy}

|Issue Type|Component|Release Note|
|--- |--- |--- |
|Bug|Media Wall|Fixed a bug that allows Facebook videos to play appropriately.|
|Bug|ModQ|Fixed a bug that prevented Email Subjects from not displaying in Email Stream Content.|
|Bug|Mosaic|Added additional accessibility support to Mosaic to allow users to shift tab between content cards.|
|Bug|Reviews|Fixed a bug that was preventing rating edits to appear appropriately.|
|Bug|Social Search|Fixed a bug that caused the Show More button to be cut off on Twitter List Search results.|
|Enhancement|Storify 2|Enhanced Storify 2 to support Copywrite Free content search. Copywrite Free searches across Flickr, Noun Project, Kuler, Pixabay and Unsplash for copywrite free images.|
|Bug|Streams|Fixed a bug that prevented Tumblr stream rules from saving.|
|Bug|Streams|Fixed a bug that produced incorrect Generator Ids in the Collection JSON for RSS Feeds.|
|Enhancement|Streams|Made an adjustment to the setting of "Verified accounts only" option to be disabled by default.|
|Enhancement|Streams|Added a new feature to allow categories of content (via a Stream Rule) to be allow-listed and bypass moderation.|
|Bug|Streams|Fixed a bug that caused "Premoderate" and "Media Premoderate" settings to carry over to a newly created Stream rule.|

## UAT Release {#section_dyx_yl2_wy}

|Issue Type|Component|Release Note|
|--- |--- |--- |
|Bug|Conversation Apps|Enhanced Conversation Apps to always link out to user profiles, even without a full auth integration.|
|Bug|Mosaic|Fixed a bug that now serves all Twitter images via HTTPS.|
|Bug|Social Search|Fixed a bug that caused the green "saved" checkmark to not appear when saving assets in Social Search and viewing assets in Library.|
|Bug|Social Search|Fixed a bug that prevented the "Conceal explicit images" option from functioning properly.|
|Enhancement|Storify 2|Enhanced Storify 2 to support permalinks opening a modal (previously the app would scroll to the post location on the page). In Storify 2's Designer, we have added a configuration to toggle between Scroll and Modal permalink behavior. Modal permalink behavior will be default behavior.|
|Enhancement|Storify 2|Enhanced the Storify 2 Google AMP integration to produce a smaller CSS file.|
|Bug|Streams|Enhanced content (images and videos) from Email Stream Rules to be available via HTTPS.|
|Bug|Streams|Added a label for the Mile Radius Value in maps in Twitter Stream Rules.|
|Bug|Streams|Fixed a bug with Facebook and Facebook Page Steam Rules to pull in posts with multiple media attachments appropriately.|
|Bug|Studio|Fixed a bug that caused multiple &'s from getting appended to the URL when using filters in Studio.|
|Bug|Studio|Fixed a bug that prevented certain checkboxes in Studio filters from allowing to be unchecked.|
