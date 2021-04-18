---
description: Release Notes for the February 23, 2017 release.
title: February 23, 2017
exl-id: 3a5708a1-4be6-447f-ae6e-8f5a37171ed7
---
# February 23, 2017{#february}

Release Notes for the February 23, 2017 release.

## Production Release

| **Issue Type** |**Component** |**Release Note** |
|---|---|---|
|  Enhancement | Android SDK | Re-organized the Android SDK to ensure that example and reference implementation directories are more clearly identifiable by their location. |
|  Enhancement | Android SDK | Android SDK modified to now support a minimum SDK version of 14 (down from 16). |
|  Bug | Conversation Apps | Enhanced Conversation Apps to always link out to user profiles, even without a full auth integration. |
|  Bug | Mosaic | Fixed a bug that now serves all Twitter images via HTTPS. |
|  Enhancement | Search and Streams | Added the ability to search by Instagram Places (check-in’s) in Library Instagram Search and Instagram Stream Rules. |
|  Bug | Settings | Fixed a bug that prevented Twitter Social Accounts from saving. |
|  Bug | Social Search | Fixed a bug that prevented the “Conceal explicit images” option from functioning properly. |
|  Enhancement | Storify 2 | Enhanced Storify 2 to support permalinks opening a modal (previously the app would scroll to the post location on the page). In Storify 2’s Designer, we have added a configuration to toggle between Scroll and Modal permalink behavior. Modal permalink behavior will be default behavior. |
|  Enhancement | Storify 2 | Enhanced the Storify 2 Google AMP integration to produce a smaller CSS file. |
|  Enhancement | Streams | Fixed a bug with Facebook rules that was causing content to be pulled in with incomplete metadata. |
|  Bug | Streams | Enhanced content (images and videos) from Email Stream Rules to be available via HTTPS. |
|  Bug | Streams | Added a label for the Mile Radius Value in maps in Twitter Stream Rules. |
|  Bug | Streams | Fixed a bug with Facebook and Facebook Page Steam Rules to pull in posts with multiple media attachments appropriately. |
|  Enhancement | Streams | Added a new feature to allow users to choose to apply or disable SAFE rules per stream rule. |
|  Enhancement | Studio | Fixed a bug that was causing content to not publish or save correctly if it already existed. |
|  Bug | Studio | Fixed a bug that caused multiple &’s from getting appended to the url when using filters in Studio. |
|  Bug | Studio | Fixed a bug that prevented certain checkboxes in Studio filters from allowing to be unchecked. |

## UAT Release

| **Issue Type** |**Component** |**Release Note** |
|---|---|---|
|  Bug | Apps | Fixed a bug to show content in media modals with the correct aspect ratios. |
|  Bug | Media Wall | Fixed a bug that was caused Media Walls to not render if specific foreign characters were included. |
|  Bug | Search | Fixed a bug that was causing pages to load incorrectly when paging through search results with “Conceal explicit images” enabled. |
|  Enhancement | Studio | Increased session time before expiring Studio User login sessions . Once a Studio session expires the user will be redirected to log in again. |
|  Bug | Studio | Fixed a bug that was sometimes preventing users from saving Instagram credentials. |
|  Bug | Studio | Fixed a bug that was preventing the “Feature Tag” to save correctly when applied. |
