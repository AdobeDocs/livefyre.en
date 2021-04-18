---
description: Release Notes for the April 26, 2018 release.
title: April 26, 2018
exl-id: af0ee64d-d60c-4b21-a628-08848313781c
---
# April 26, 2018{#april}

Release Notes for the April 26, 2018 release.

## New Features {#section_syx_mdt_wcb}

The following features are new in the production version of this release:

* Added a new feature that enables customers to configure a specific number of columns for a Media Wall. The number of columns you choose will force the Media Wall into that number of columns, regardless of size. Otherwise, the number of Media Wall columns defaults to "auto" where the columns adjust to a number that optimizes Media Wall for the screen size.
* In the Media Wall Designer there is now a toggle that allows you to turn off the automatic Media Wall animation that occurs when a page with a Media Wall loads.
* You can now choose the confidence threshold for smart tags in streams. Setting the precision score (0-100) for tags allows you to control the accuracy of the assets we are retrieving.
* Added moderation recommendations. Livefyre now scans every post in commenting Apps and predicts whether you will trash it or not based on historical data and machine learning. These recommendations appear in ModQ.
  * Users can turn off moderation recommendations, which allow users to filter ModQ by the content Livefyre thinks you will trash.
  * Added the ability to filter ModQ by the moderation recommendation tag, Trash.

## Issues {#section_ehw_ndt_wcb}

The issues in the following tables were resolved in this release.

## Production Release

|  **Issue Type** | **Component** | **Release Note** |
|---|---|---|
|  Bug | Rights Management | Fixed an issue where rights requests weren't working for Assets after finding them in a Social Search. |
|  Enhancement | Streams | Updated the streaming mechanism that allows content to stream from Facebook to comply with a back-end change created by Facebook.  |
|  Bug | UGC Commerce | Fixed an issue where the CTA "Shop" button did not display in a Mosaic or Filmstrip App or a products modal when hovering over a card with a product when the CTA button is enabled. |
|  Enhancement | UGC Commerce | Fixed an issue where the UGC Commerce flag was set to &quot;off&quot; by default, instead of &quot;on.&quot;  |

## UAT Release

|  **Issue Type** | **Component** | **Release Note** |
|---|---|---|
|  Bug | Library/Search | Fixed an issue with videos not uploading properly. |
|  Enhancement | Studio | Added the ability to see suggested words when typing in tag names.  |
