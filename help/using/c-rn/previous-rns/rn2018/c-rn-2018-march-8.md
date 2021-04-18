---
description: Release Notes for the March 8, 2018 release.
title: March 8, 2018
exl-id: 46d4a425-17e0-48a2-a596-5cc7163f9edd
---
# March 8, 2018{#march}

Release Notes for the March 8, 2018 release.

## New Features {#section_syx_mdt_wcb}

The following features are new in the production version of this release:

* **Deleting Apps. **Added the ability to delete Apps in Studio so users can better manage the App list. Deleting an App removes it from the table, but it does not remove the App from your site. The App will keep receiving content from a stream if it is configured to do so.

## Issues {#section_ehw_ndt_wcb}

The issues in the following tables were resolved in this release.

## Production Release

|  **Issue Type** | **Component** | **Release Note** |
|---|---|---|
|  Bug | Polls | Changed Polls to use HTTPS exclusively. Previously, Polls were still allowed to be used with HTTP.  |
|  Bug | Studio | Fixed an issue that caused the modal window that displays announcements when you log into Studio to display too large on low resolution screens. |

## UAT Release

|Issue Type|Component|Release Note|
|--- |--- |--- |
|Enhancement|Filmstrip|Updated the following accessibility features for Filmstrip: <br><ul><li>Left/right arrows corrected from &lt;div&gt; to &lt;button&gt; </li><li>Preview image element changed from a less-descriptive ARIA label of, "Open attached photo," to a label that reads the name of the platform and the post text.</li></ul>|
|Bug|Media Wall|Fixed an issue in Media Wall where tags were not clickable when an Instagram post was added from a stream rule.|
|Enhancement|Media Wall|Improved Media Wall accessibility in the following ways: <br><ul><li>Opening and closing modals via keyboard commands will no longer shift focus back to the top of the page. Focus instead remains on the element last focused before modal popup.</li><li>Load More button can be tabbed to and triggered using the keyboard Enter key.</li></ul>|
|Bug|Rights Management|Fixed an error where you couldn't see the rights request modal after rights for an Instagram asset were granted.|
