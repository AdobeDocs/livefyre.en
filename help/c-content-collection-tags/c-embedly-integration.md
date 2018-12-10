---
description: Use embed.ly to display multiple media formats, directly in the App.
seo-description: Use embed.ly to display multiple media formats, directly in the App.
seo-title: Embedly Integration
solution: Experience Manager
title: Embedly Integration
uuid: e84cd2ef-4a6e-4aab-a9be-ca988e16309c
index: y
internal: n
snippet: y
---

# Embedly Integration{#embedly-integration}

Use embed.ly to display multiple media formats, directly in the App.

To better enable embedded media content from a variety of sources, including Google Maps, YouTube, Flickr, Facebook, Instagram, Spotify, and Tumblr, Livefyre Apps use Embedly as a third-party provider for URL expansion. If a user or moderator includes a supported link in a post, the media included in the link will expand when posted to the Collection.

This provides Livefyre Apps with access to the more than 250 different embedded media options that Embedly supports.

>[!NOTE]
>
>Livefyre expands only a subset of Embedly’s full provider list. Embedded images will expand on HTTPS pages only if the provider is Twitter, YouTube, Imgur, Vine, Wikipedia, or SoundCloud. Please contact your Technical Account Manager for any further questions about link expansion or sources.

This page lists examples of some popular embedded media types, and their acceptable URL patterns. Embed.ly is continually adding new sources. For a complete list of providers, please go to http://embed.ly/embed/features/providers.

>[!NOTE]
>
>The Embedly formatting requires a full permalink. Shortened links will not work.

Only publicly viewable content is embeddable. If you attempt to embed a piece of content that is not public, the link to the content will appear in the blog post, and a placeholder icon will accompany it. When clicked, the link will take the reader to an error message from the service where the content is hosted, such as a Facebook message for a friends-only photo. Please contact your Account Manager if you notice that media is not expanded as expected.

#### Sample Embedly URLs
<table id="table_lth_m4x_vy">  
 <tbody> 
  <tr> 
   <td><b>Maps</b></td> 
   <td><b>Google Maps</b></td> 
   <td> 
    <ul id="ul_mth_m4x_vy"> 
     <li>http://maps.google.com/maps?*</li> 
     <li>http://maps.google.com/?*</li> 
     <li>http://maps.google.com/maps/ms?*</li> 
     <li><b>Note: </b>URL must begin with “http” and not “https.”</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td><b>Social Networking</b></td> 
   <td><b>Google Plus</b></td> 
   <td> 
    <ul id="ul_nth_m4x_vy"> 
     <li>http://plus.google.com/*</li> 
     <li>http://www.google.com/profiles/*</li> 
     <li>https://plus.google.com/*</li> 
     <li>http://google.com/profiles/*</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td></td> 
   <td><b>YouTube</b></td> 
   <td> 
    <ul id="ul_oth_m4x_vy"> 
     <li>http://*youtube.com/watch*</li> 
     <li>http://*.youtube.com/v/*</li> 
     <li>https://*youtube.com/watch*</li> 
     <li>https://*.youtube.com/v/*</li> 
     <li>http://youtu.be/*</li> 
     <li>http://*.youtube.com/user/*</li> 
     <li>http://*.youtube.com/*#*/*</li> 
     <li>http://m.youtube.com/watch*</li> 
     <li>http://m.youtube.com/index*</li> 
     <li>http://*.youtube.com/profile*</li> 
     <li>http://*.youtube.com/view_play_list*</li> 
     <li>http://*.youtube.com/playlist*</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td><b>Photos</b></td> 
   <td><b>Flickr</b></td> 
   <td> 
    <ul id="ul_pth_m4x_vy"> 
     <li>http://www.flickr.com/photos/*</li> 
     <li>http://flic.kr/*</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td></td> 
   <td><b>Instagram</b></td> 
   <td> 
    <ul id="ul_qth_m4x_vy"> 
     <li>http://instagr.am/p/*</li> 
     <li>http://instagram.com/p/*</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td></td> 
   <td><b>TwitPic</b></td> 
   <td> 
    <ul id="ul_rth_m4x_vy"> 
     <li>http://twitpic.com/*</li> 
     <li>http://www.twitpic.com/*</li> 
     <li>http://twitpic.com/photos/*</li> 
     <li>http://www.twitpic.com/photos/*</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td></td> 
   <td><b>Facebook</b></td> 
   <td> 
    <ul id="ul_sth_m4x_vy"> 
     <li>http://www.facebook.com/photo.php*</li> 
     <li>https://www.facebook.com/photo.php*</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td></td> 
   <td> <p><b>Ow.ly </b></p> <p>(Hootsuite’s Content Uploading Service)</p> </td> 
   <td> 
    <ul id="ul_tth_m4x_vy"> 
     <li>http://ow.ly/i/*</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td><b>Polls</b></td> 
   <td><b>GoPollGo</b></td> 
   <td> 
    <ul id="ul_uth_m4x_vy"> 
     <li>http://gopollgo.com/*</li> 
     <li>http://www.gopollgo.com/*</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td></td> 
   <td><b>Droplr</b></td> 
   <td> 
    <ul id="ul_vth_m4x_vy"> 
     <li>http://d.pr/i/*</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td><b>Audio</b></td> 
   <td><b>SoundCloud</b></td> 
   <td> 
    <ul id="ul_wth_m4x_vy"> 
     <li>http://soundcloud.com/*</li> 
     <li>http://soundcloud.com/*/*</li> 
     <li>http://soundcloud.com/*/sets/*</li> 
     <li>http://soundcloud.com/groups/*</li> 
     <li>http://snd.sc/*</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td></td> 
   <td><b>Spotify</b></td> 
   <td> 
    <ul id="ul_xth_m4x_vy"> 
     <li>http://open.spotify.com/*</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td><b>Blogs</b></td> 
   <td><b>Tumblr</b></td> 
   <td> 
    <ul id="ul_yth_m4x_vy"> 
     <li>http://tumblr.com/*</li> 
     <li>http://*.tumblr.com/post/*</li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

Apps that use this feature:

* [Carousel](../c-carousel-app/c-carousel-app.md#c_carousel_app)
* [Chat](../c-chat-app/c-chat-app.md#c_chat_app)
* [Comments](c_comments_app.md#c_comments_app)
* [Feature Card](../c-feature-card-app/c-feature-card-app.md#c_feature_card_app)
* [Map](../c-map-app/c-map-app.md#c_map_app)
* [Media Wall](../c-media-wall-app/c-media-wall-app.md#c_media_wall_app)
* [Mosaic](../c-mosaic-app/c-mosaic-app.md#c_mosaic_app)
* [Polls](../c-polls-app/c-polls-app.md#c_polls_app)
* [Reviews](../c-reviews-app/c-reviews-app.md#c_reviews_app)
* [Sidenotes](../c-sidenotes-app/c-sidenotes-app.md#c_sidenotes_app)
* [Storify 2](../c-storify2/c-storify2.md#c_storify2)
* [Trending](../c-trending-app/c-trending-app.md#c_trending_app)
* [Upload Button](../c-upload-button-app/c-upload-button-app.md#c_upload_button_app)
