---
description: Release Notes for the August 9, 2018 release.
seo-description: Release Notes for the August 9, 2018 release.
seo-title: August 9, 2018
solution: Experience Manager
title: August 9, 2018
uuid: c59ae5ec-9d26-41c4-9a98-cb95c89ee26a
exl-id: 7b2fb562-33bf-4c34-ab83-5fc34f5d1f4f
---
# August 9, 2018{#august}

Release Notes for the August 9, 2018 release.

## New Features {#section_syx_mdt_wcb}

**Video Smart Tags:** Users can now see smart tags for videos under 50MB.

## Issues {#section_ehw_ndt_wcb}

The issues in the following tables were resolved in this release.

## Production Release

|  **Issue Type** | **Component** | **Release Note** |
|---|---|---|
|  Bug | App Content | Fixed an issue that prevented administrators and content managers to edit content in App Content.  |
|  Enhancement | Apps | Social networks have made privacy changes that mean social mentions will no longer be supported for Facebook or Twitter.  |
|  Enhancement | Apps | Social networks have made privacy changes. The "Post To" feature that automatically posts content to social networks (Facebook, LinkedIn, Twitter) has been removed. |
|  Enhancement | GDPR | Removed the toggle for details mode from the request details page under Settings > Privacy. Details mode toggle can still be accessed by adding /dbg at the end of the URL.  |
|  Bug | Integration: AEM | Fixed an issue where drag and dropping Livefyre Apps in AEM appeared to create multiple Apps.  |
|  Bug | Library | Fixed an issue where an asset didn't save properly in the library.  |
|  Bug | Livefyre Identity | Fixed an issue with LF identity that caused 403 errors when signing in. |
|  Bug | Social Search | Fixed an issue where users were unable to search for public Facebook posts using the URL option in Social Search. |
|  Enhancement | Social Sync | Social networks have made privacy changes that mean Social Sync will no longer be supported for Facebook.  |
|  Enhancement | Streams | Now, when you delete an App, you delete all streams associated with that App.  |
|  Enhancement | Studio | Customers now have the ability to emit Livefyre events to Adobe Analytics individually as opposed to in batches.  |
|  Enhancement | Studio | Modal windows that display in conversation Apps for social networks will now be modal windows from the social network instead of Adobe Experience Manager Livefyre or other branded modal windows.  |

## UAT Release

The issues in the following tables were resolved in the UAT version release.

|  **Issue Type** | **Component** | **Release Note** |
|---|---|---|
|  Bug | GDPR | Fixed an issue where opt-out messages were not displaying for some Instagram videos.  |
|  Bug | Library | Fixed an issue where a card with rights granted manually displayed the wrong rights request status. |
|  Bug | Library | Fixed an issue where an asset could not be saved to a folder.  |
|  Bug | Library/Search | Restored the ability to search URLs from Instagram in Social Search. |
|  Bug | ModQ | Fixed an issue where More Info Menu in ModQ did not display where expected. |
|  Bug | Rights Management | Fixed an issue where sorting in ModQ should be in a fixed position when page is scrolling. |
|  Bug | Streams | Fixed an issue with viewing streams on staging environment. |
|  Enhancement | Streams | Added a Safe For Work (SFW) and Not Safe For Work (NSFW) toggle to Streams. |
|  Enhancement | Studio | Added smart tag functionality to content uploaded to Livefyre Studio Library via FileStack (upload functionality in All Assets). |
