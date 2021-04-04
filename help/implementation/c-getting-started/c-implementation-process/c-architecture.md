---
description: Learn Livefyre conventions and how Livefyre organizes content.
seo-description: Learn Livefyre conventions and how Livefyre organizes content.
seo-title: Architecture
solution: Experience Manager
title: Architecture
uuid: 94358e6c-954a-4a52-9bb2-d800b2933130
exl-id: d4fe12d1-117a-4aae-90ff-e9ebdd6c5bac
---
# Architecture{#architecture}

Learn Livefyre conventions and how Livefyre organizes content.

This section provides an overview of the Livefyre Network Architecture.

## Networks and Sites Overview

Livefyre organizes users and content by network and site. Every network may have one or more user accounts associated with it, and each network may include one or more Livefyre sites. A Livefyre site is an arbitrary grouping of Collections. One Collection maps to one article ID in your CMS.

## Understanding Networks {#section_hqt_4m4_xz}

Customers with multiple domains can share user accounts across all domains, using a single Livefyre network. Customers that want to keep separate user accounts for different domains will require separate Livefyre networks.

Configuration settings can apply to sites, networks and Collections (referred to as conversation in the illustration above).

>[!NOTE]
>
>Some settings are available only at the network level (such as email notification preferences, email from address, and email custom logos). If you’d like these settings to be different for each domain, you must use multiple networks.

## Understanding Sites {#section_vjw_nm4_xz}

A site is an arbitrary grouping of articles. The grouping is useful as it allows you to assign different moderators to different groups of content. Moderators and owners may be set up to moderate content and configure admin settings at either the network or the site level. If you would like some moderators to only see certain Collections, these Collections may be set up as a separate Livefyre site.

>[!NOTE]
>
>There is no limit to the number of sites you may have under your custom network.

## App Sequence Diagram {#section_mw2_lm4_xz}

Whether you’re looking to implement custom function with Livefyre provided endpoints, or simply need to debug an issue, it helps to understand how the Livefyre app request/response flow works.

![](assets/appsequencediagram.png)

1. When your client hits your site, instantiate the Livefyre app with the Site ID and Article ID.
1. If you wish to authenticate the user (valuable for traffic evaluation, as well as site-protection), send Livefyre the site information, and User Profile token.
1. Send Livefyre the Site ID and Article ID to initialize the App.

   Livefyre returns the initial content.

   Send this content to the page, and display the App.

1. To update content displayed on the page, send Livefyre the latest Event ID from your page. If any new content is available, it will be returned.

   Reload your page with new content, and repeat the process indefinitely.

1. If you allow users to post new content, trigger an event when new content is posted on your site to post the content to Livefyre. Livefyre will return an updated stream, which you can use to update your site.
