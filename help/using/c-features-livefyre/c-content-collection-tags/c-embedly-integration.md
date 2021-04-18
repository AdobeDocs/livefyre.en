---
description: Use embed.ly to display multiple media formats, directly in the App.
title: Embedly Integration
exl-id: 859fe306-367e-4207-b9f7-c730ba0cd24d
---
# Embedly Integration{#embedly-integration}

Use `embed.ly` to display multiple media formats, directly in the App.

To better enable embedded media content from a variety of sources, including Google Maps, YouTube, Flickr, Facebook, Instagram, Spotify, and Tumblr, Livefyre Apps use Embedly as a third-party provider for URL expansion. If a user or moderator includes a supported link in a post, the media included in the link will expand when posted to the Collection.

This provides Livefyre Apps with access to the more than 250 different embedded media options that Embedly supports.

>[!NOTE]
>
>Livefyre expands only a subset of Embedly’s full provider list. Embedded images will expand on HTTPS pages only if the provider is Twitter, YouTube, Imgur, Vine, Wikipedia, or SoundCloud. Please contact your Technical Account Manager for any further questions about link expansion or sources.

This page lists examples of some popular embedded media types, and their acceptable URL patterns. `Embed.ly` is continually adding new sources. For a complete list of providers, please go to `https://embed.ly/embed/features/providers`.

>[!NOTE]
>
>The Embedly formatting requires a full permalink. Shortened links will not work.

Only publicly viewable content is embeddable. If you attempt to embed a piece of content that is not public, the link to the content will appear in the blog post, and a placeholder icon will accompany it. When clicked, the link will take the reader to an error message from the service where the content is hosted, such as a Facebook message for a friends-only photo. Please contact your Account Manager if you notice that media is not expanded as expected.

## Sample Embedly URLs

|Type|Provider|URLs|
|--- |--- |--- |
|Maps|Google Maps|<ul><li>`https://maps.google.com/maps?*`</li><li>`https://maps.google.com/?*`</li><li>`https://maps.google.com/maps/ms?*`</li></ul><br>**Note**: URL must begin with `http` and not `https.`|
|Social Networking|Google Plus |<ul><li>`https://plus.google.com/*`</li><li>`https://www.google.com/profiles/*`</li><li> `https://plus.google.com/*`</li><li>`https://google.com/profiles/*`</li></ul> |
| Video | YouTube | <ul><li>`https://*youtube.com/watch*`</li><li> `https://*.youtube.com/v/*`</li><li>`https://*youtube.com/watch*` </li><li>`https://*.youtube.com/v/*`</li><li>`https://youtu.be/*`</li><li>`https://*.youtube.com/user/*` </li><li>`https://*.youtube.com/*#*/*`</li><li>`https://m.youtube.com/watch*`</li><li>`https://m.youtube.com/index*`</li><li>`https://*.youtube.com/profile*`</li><li>`https://*.youtube.com/view_play_list*`</li><li>`https://*.youtube.com/playlist*`</li></ul>|
|Photos|Flickr|`https://www.flickr.com/photos/*`<br>`https://flic.kr/*`|
||Instagram|`https://instagr.am/p/*`<br>`https://instagram.com/p/*`|
||TwitPic|<ul><li>`https://twitpic.com/*`</li><li>`https://www.twitpic.com/*`</li><li>`https://twitpic.com/photos/*`</li><li>`https://www.twitpic.com/photos/*`</li></ul>|
||Facebook|`https://www.facebook.com/photo.php*`|
||`Ow.ly` (Hootsuite’s Content Uploading Service)|`https://ow.ly/i/*`|
|Polls|GoPollGo|`https://gopollgo.com/*`<br>`https://www.gopollgo.com/*`|
||Droplr|`https://d.pr/i/*`|
|Audio|SoundCloud|<ul><li>`https://soundcloud.com/*`</li><li>`https://soundcloud.com/*/*` </li><li>`https://soundcloud.com/*/sets/*` </li><li>`https://soundcloud.com/groups/*` </li><li>`https://snd.sc/*`</li></ul>|
||Spotify|`https://open.spotify.com/*`|
|Blogs|Tumblr|`https://tumblr.com/*`<br>`https://*.tumblr.com/post/*`|

Apps that use this feature:

* [Carousel](/help/using/c-about-apps/c-carousel-app/c-carousel-app.md#c_carousel_app)
* [Chat](/help/using/c-about-apps/c-chat-app/c-chat-app.md#c_chat_app)
* [Comments](/help/using/c-about-apps/c-comments/c-comments.md)
* [Feature Card](/help/using/c-about-apps/c-feature-card-app/c-feature-card-app.md#c_feature_card_app)
* [Map](/help/using/c-about-apps/c-map-app/c-map-app.md#c_map_app)
* [Media Wall](/help/using/c-about-apps/c-media-wall-app/c-media-wall-app.md#c_media_wall_app)
* [Mosaic](/help/using/c-about-apps/c-mosaic-app/c-mosaic-app.md#c_mosaic_app)
* [Polls](/help/using/c-about-apps/c-polls-app/c-polls-app.md#c_polls_app)
* [Reviews](/help/using/c-about-apps/c-reviews-app/c-reviews-app.md#c_reviews_app)
* [Sidenotes](/help/using/c-about-apps/c-sidenotes-app/c-sidenotes-app.md#c_sidenotes_app)
* [Storify 2](/help/using/c-about-apps/c-storify2/c-storify2.md#c_storify2)
* [Trending](/help/using/c-about-apps/c-trending-app/c-trending-app.md#c_trending_app)
* [Upload Button](/help/using/c-about-apps/c-upload-button-app/c-upload-button-app.md#c_upload_button_app)
