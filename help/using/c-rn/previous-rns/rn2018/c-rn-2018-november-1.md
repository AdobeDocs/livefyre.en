---
description: Release Notes for the November 1, 2018 release.
seo-description: Release Notes for the November 1, 2018 release.
seo-title: November 1, 2018
solution: Experience Manager
title: November 1, 2018
uuid: ed1a3bf1-b3f1-4746-8462-07283723ba62
exl-id: b12b6a56-f14f-4447-9fde-25cb3acf6665
---
# November 1, 2018{#november}

Release Notes for the November 1, 2018 release.

## New Features {#section_syx_mdt_wcb}

The following new features were released in the production version of this release:

* Video Smart Tags

  Leverage state of the art computer vision technology, powered by Adobe Sensei, to automatically tag video content when you save it to the Library. Smart Tags help you manage UGC more effectively but also create super precise curation rules (streams) that collect content based on what's in the video, not just the text, saving you significant effort moderating unwanted content.

  Feature details:

    * Smart tags are automatically added to videos gained from social search, streams, and uploaded video files in the Library. View tags in the asset details for an individual video
    * Tags videos in .MP4, .MOV, and AVI formats
    * Tags videos up to 60 seconds or 50MB
    * Two categories of smart tags apply to videos: features ( animals, objects, places, etc) and actions (running, walking, singing, etc.)

  For more information see [Smart Tags](/help/using/c-features-livefyre/c-smart-tags/c-smart-tags.md#c_smart_tags)

* Instagram Rate Limiting

  Instagram has changed the number of requests that any company using the Instagram API, including Livefyre, can make from 5,000 requests per hour per token to 200 requests an hour per token. This is known as *rate limiting*. For more information, see [Instagram Rate Limiting](/help/using/c-streams/c-instagram-rate-limiting.md).

* Audio Files in the Library

  You can now perform the following functions on audio files from the library panel:

    * Search
    * Preview
    * Import
    * Filter by audio files
    * Drag and drop files into the designer

## Issues {#section_ehw_ndt_wcb}

No new issues were resolved in the production version of this release. See [section above](#c_rn/section_syx_mdt_wcb).

## UAT Release {#section_EE91B0C9313E45C5B4CBD59CFBCCFCFE}

The issues in the following tables were resolved in the UAT version of this release.

|  **Issue Type** | **Component** | **Release Note** |
|---|---|---|
|  Enhancement | GDPR | All data attributed to former customers within Analytics will be deleted. |
|  Bug | Library | Fixed an issue where a video uploaded to the Library, then viewed in asset detail did not display correctly. |
|  Bug | Mosaic | Fixed an issue where a Mosaic displayed the last piece of content from an Instagram carousel as a thumbnail, instead of a card.  |
|  Bug | Social Search | Fixed an issue where Instagram social searching didn't work as expected.  |
