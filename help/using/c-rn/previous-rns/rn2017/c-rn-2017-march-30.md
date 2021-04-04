---
description: Release Notes for the March 30, 2017 release.
seo-description: Release Notes for the March 30, 2017 release.
seo-title: March 30, 2017
title: March 30, 2017
uuid: 2adf04a9-6c52-4fa1-a0c9-b2d3886305e9
exl-id: 44c73ff9-8bc1-49c9-b720-aff425e5cd28
---
# March 30, 2017{#march}

Release Notes for the March 30, 2017 release.

## Production Release

|  Issue Type | Component | Release Note |
|---|---|---|
|  Bug | Social Search | Fixed a bug that prevented saved Youtube assets in Social Search from publishing. |
|  Enhancement | Social Sync | Deprecated Twitter Social Sync. |
|  Enhancement | Storify 2 | Added an enhancement to display the message "No results found" on Facebook Topic search when no results are found. |
|  Enhancement | Streams | Added Summary Rules for SAFE Rules to the bottom of a Twitter Stream page. |
|  Bug | Streams | Added an enhancement to visibly disable the "verified user" checkbox on Twitter Stream Rules when excluded authors are provided. |
|  Bug | Streams | Fixed a bug to allow the usage of ANDing keywords and a Location filter in a Twitter rule. |
|  Bug | Studio | Fixed a bug that was preventing the "Feature Tag" to save correctly when applied. |

## UAT Release

|  Issue Type | Component | Release Note |
|---|---|---|
|  Bug | App Content | Changed the behavior of "More Info" such that if there are multiple Anonymous flag events on a given piece of content, the earliest event is always shown. |
|  Bug | Library | Fixed a bug that caused Library searches with hashtags to intermittently fail. |
|  Bug | Maps | Fixed a bug in Maps to support a large number of content in clusters on iOS devices. |
|  Enhancement | Mosaic | Added the ability to configure Mosaic apps to click anywhere on a content card to open the modal by animation type `none` in designer and `cardAnimation: 'off'`if instantiated through the SDK. |
|  Bug | Mosaic | Fixed a bug to allow users to successfully make changes to Mosaic apps in Designer. |
|  Enhancement | Rights Request | Added a new rights request status called "Request Failed" to highlight when rights request messages fail to send. |
|  Enhancement | Settings | Added the ability for customers to create Spam Moderation Rules in Settings. |
|  Enhancement | Social Search | Fixed a bug that prevented VK.com posts from displaying via URL Social Searches. |
|  Enhancement | Social Search | When searching for Instagram content from Studio, if the search is due to an expired Instagram API Token, the error message will now indicate as such. |
|  Bug | Streams | Fixed a bug that caused an "App is not accepting new content" banner to falsely display on top of Stream Rule pages. |
|  Enhancement | Streams | Modified the default of newly created stream rules to Apply SAFE Rules when applicable. |
|  Enhancement | Streams (formerly, Curate Rules) | Removed the "Vines" only option from Twitter Stream/Curate rules, as Vines are now displayed as Twitter videos. |
|  Bug | Studio Shell | Fixed a bug so that Livefyre Studio will load if https:// was explicitly prepended to the url. |
