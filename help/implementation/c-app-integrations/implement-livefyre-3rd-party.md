---
description: Create Livefyre Apps from scratch to create customized experiences and data visualizations.
seo-description: Create Livefyre Apps from scratch to create customized experiences and data visualizations.
seo-title: Integrate Livefyre with Third Party Integration
solution: Experience Manager
title: Integrate Livefyre into a CMS
uuid: 5a3e18e8-8568-45bb-9070-d0fa43dd819b
exl-id: 05d85792-de97-47b1-90cc-ad7e841754b5
---
# Implement Livefyre with Third Party Integration

Create Livefyre Apps from scratch to create customized experiences and data visualizations.

You can create a Livefyre App from scratch by consuming Livefyre and social data using the Bootstrap and Stream API.

For Livefyre Apps that require authentication, see Identity Integration for information about supported third party authentication platforms.

To implement Conversation Apps (Comments, Chat, Live Blog, Sidenotes):

1. Perform App integration.
  a. Create a Collection Using the CollectionMeta Token.
  b. Integrate Livefyre Apps to sites using the Livefyre.js embed code structure. 

    * For more information on how to use the Livefyre.js embed code structure, see [Embed an App](/help/implementation/c-getting-started/c-implementation-process/c-using-livefyre.js-to-create-customize-and-use-apps-on-your-site.md).
  
    * For information on how to integrate the Comments App, see [Comments](/help/using/c-about-apps/c-comments/c-comments.md).
  
    * For information on how to integrate the Chat App, see [Chat](/help/using/c-about-apps/c-chat-app/c-chat-app.md).
  
    * For information on how to integrate the Live Blog App, see [Live Blog](/help/using/c-about-apps/c-liveblog-app/c-liveblog-app.md).
  
    * For information on how to integrate the Sidenotes App, see [Sidenotes](/help/using/c-about-apps/c-sidenotes-app/c-sidenotes-app.md).

1. Perform authentication integration.
  a. Create User Auth tokens to pass and store user data in Livefyre.
  b. Integrate third party user and authentication platforms. For a list of supported platforms, see [Identity Integration](/help/implementation/t-about-identity-integration/t-about-identity-integration.md).

1. Perform App customizations. App Customizations options to match your branding and style and add custom functionality.

To create a visualization App (Map, Media Wall, Trending, Carousel, Filmstrip, Storify, Feature Card, Mosaic, Polls):

1. Perform App integration.
  a. Create a Collection Using the CollectionMeta Token.
  b. Integrate Livefyre Apps to sites using the Livefyre.js embed code structure. For more information on how to use the Livefyre.js embed code structure, see [Embed an App](/help/implementation/c-getting-started/c-implementation-process/c-using-livefyre.js-to-create-customize-and-use-apps-on-your-site.md).

    * For information on how to integrate the Map App, see [Map](/help/using/c-about-apps/c-map-app/c-map-app.md).

    * For information on how to integrate the Media Wall App, see [Media Wall](/help/using/c-about-apps/c-media-wall-app/c-media-wall-app.md).

    * For information on how to integrate the Trending App, see [Trending](/help/using/c-about-apps/c-trending-app/c-trending-app.md).

1. Perform authentication integration.
 a. Create User Auth tokens to pass and store user data in to Livefyre.
 b. Integrate third party user and authentication platforms. For a list of supported platforms, see [Identity Integration](/help/implementation/t-about-identity-integration/t-about-identity-integration.md).

>[!NOTE]
>
>Livefyre does not support Carousel, Filmstrip, Storify, Feature Card, Mosaic, and Polls Apps using Livefyre.js.

Integrate these Apps using the [Create an App](/help/using/c-about-apps/c-create-an-app.md) process.
