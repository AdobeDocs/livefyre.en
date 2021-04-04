---
description: Release Notes for the February 15, 2018 release.
seo-description: Release Notes for the February 15, 2018 release.
seo-title: February 15, 2018
solution: Experience Manager
title: February 15, 2018
uuid: ee46f088-9fb7-49e2-a42c-e0d4b2f24a32
exl-id: 7276de37-c8cd-4e85-bc92-90c272e5bf94
---
# February 15, 2018{#february}

Release Notes for the February 15, 2018 release.

## New Features {#section_syx_mdt_wcb}

The following features are new in the production version of this release:

* **Smart Tags.**

  Livefyre uses Adobe Sensei image-recognition technology to automatically tag images you save in the library.
  With Smart Tags you can save a significant amount of time searching and moderating content. With Smart Tags, you can:

  * Search saved images for precise content based on the image content, rather than only text
  * Collect content in streams based on precise search terms that analyze the image, rather than only text

  For more information about Smart Tags, see [Smart Tags](/help/using/c-features-livefyre/c-smart-tags/c-smart-tags.md#c_smart_tags).

* **In-product messages.** Now when you log in to Livefyre Studio, an announcements window pops up to display updates about new features. 
* **UGC for Carousel.** You can now use all the functions of UGC Commerce in the Livefyre Carousel App. You can create a Call-to-Action Button and connect your product catalog to the App to create a shoppable experience from Carousel.

## Issues {#section_ehw_ndt_wcb}

The issues in the following tables were resolved in this release.

## Production Release

|  **Issue Type** | **Component** | **Release Note** |
|---|---|---|
|  Issue | ModQ | Fixed an issue where Instagram posts marked as approved or trashed were re-entering the queue. |
|  Enhancement | Rights Management | Added an enhancement to display a warning when attempting to use expired Instagram accounts while making Rights Requests. |
|  Issue | Trends | Fixed an issue with the Trends App still allowing HTTP at times, rather than HTTPS. |

## UAT Release

|  **Issue Type** | **Component** | **Release Note** |
|---|---|---|
|  Enhancement | Apps | Added the ability to delete Apps from Livefyre. |
|  Issue | Polls | Changed Polls to use HTTPS exclusively. Previously, Polls were still allowed to be used with HTTP. |
|  Issue | UGC | Fixed an issue where UGC in a visualization App did not filter by Product ID as expected. |
