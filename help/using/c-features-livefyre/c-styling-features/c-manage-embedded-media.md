---
description: Define the sources from which users may post media, and those from which media posts will be banned.
title: Manage Embedded Media
exl-id: f0cc257b-cc82-47bc-9d42-6aef3e0fe8a7
---
# Manage Embedded Media{#manage-embedded-media}

Define the sources from which users may post media, and those from which media posts will be banned.

By default, all media attachments can be embedded into comments. For a comprehensive list of supported providers, see embed.ly/providers.

Livefyre uses Embed.ly, and standard oEmbed protocols, to embed media in App streams, and will pass through all media data provided by its source.

Embed.ly will pass through all available information, including the media’s title, description, thumbnail, and embed code for any provided URL. The availability of these items varies by provider. For example: Facebook does not return thumbnails for its videos, and passes only an embeddable video. Clicking Play will start the video (similar to YouTube’s display format). Twitter passes only static images, and does not send down videos. Therefore, Twitter native videos may not be played from within a Livefyre stream.

You may prevent certain attachments from being embedded into comments when embedding the comment stream. You may also choose to hide all Embed.ly expansions on the network, site and conversation level using Studio, displaying only links to the media, not fully embedded media.

Apps that use this feature:

* [Feature Card](/help/using/c-about-apps/c-feature-card-app/c-feature-card-app.md#c_feature_card_app) 
* [Map](/help/using/c-about-apps/c-map-app/c-map-app.md#c_map_app) 
* [Media Wall](/help/using/c-about-apps/c-media-wall-app/c-media-wall-app.md#c_media_wall_app)
