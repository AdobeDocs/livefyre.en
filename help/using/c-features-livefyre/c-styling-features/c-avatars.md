---
description: Allow users to customize the image that displays with their content.
title: Avatars
exl-id: cff7f6be-3660-4d71-949b-6ac04379d68d
---
# Avatars{#avatars}

Allow users to customize the image that displays with their content.

User avatars are displayed (by default) next to content in all Apps, and are pulled from the identity profile system used in your implementation. These avatars vary in size, according to the App in which they are displayed.

(Livefyre allows you to Disable Avatars if you do not wish to display them in your Apps.)

>[!NOTE]
>
>Avatars are displayed at 25p x 25p for Chat, and 50p x 50p within most other Apps.

## Avatar storage {#section_zbh_x1f_wy}

Avatars are loaded asynchronously in Livefyre. When a user first signs into the App, or changes their associated avatar image file, their profile image is added to a task queue. (A default avatar is displayed temporarily while your user’s is uploaded to the Livefyre avatar storage location.)

## Gravatars {#section_mqh_p1f_wy}

Livefyre supports the use of Gravatars. If a user does not have a custom avatar as part of their user profile, Livefyre will check for a Gravatar for that user. If no Gravatar exists, the default avatar will be used.


Apps that use this feature:

* [Carousel](/help/using/c-about-apps/c-carousel-app/c-carousel-app.md#c_carousel_app)
* [Chat](/help/using/c-about-apps/c-chat-app/c-chat-app.md#c_chat_app)
* [Comments](/help/using/c-about-apps/c-comments/c-comments.md)
* [Feature Card](/help/using/c-about-apps/c-feature-card-app/c-feature-card-app.md#c_feature_card_app)
* [Map](/help/using/c-about-apps/c-map-app/c-map-app.md#c_map_app)
* [Media Wall](/help/using/c-about-apps/c-media-wall-app/c-media-wall-app.md#c_media_wall_app)
* [Mosaic](/help/using/c-about-apps/c-mosaic-app/c-mosaic-app.md#c_mosaic_app)
* [Reviews](/help/using/c-about-apps/c-reviews-app/c-reviews-app.md#c_reviews_app)
* [Storify 2](/help/using/c-about-apps/c-storify2/c-storify2.md#c_storify2)
