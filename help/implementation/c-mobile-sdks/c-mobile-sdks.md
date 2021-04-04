---
description: Add Livefyre to your native mobile apps.
seo-description: Add Livefyre to your native mobile apps.
seo-title: Mobile SDKs
solution: Experience Manager
title: Mobile SDKs
uuid: 84c7ca1c-3401-492a-bfa5-62b996947a44
exl-id: e05001a4-6199-4d98-a661-123e031b657b
---
# Mobile SDKs{#mobile-sdks}

Add Livefyre to your native mobile apps.

There are several options available for mobile implementations, depending on the extent of customization you plan to make:

* Mobile Web Apps
* Livefyre Android or iOS SDKs
* HTTP APIs

## Mobile Web Apps {#section_t2k_vpb_11b}

Customers that open a web page on a mobile device automatically get a Livefyre content stream that is optimized for mobile, including styling to fit the reduced screen size and modifications to handle touch events.

>[!NOTE]
>
>When using a Livefyre App in an Android WebView, the Android [WebSettings.setDomStorageEnabled](https://developer.android.com/reference/android/webkit/WebSettings.html) parameter must be set to true. If localStorage is not enabled, Livefyre will not be able to log a user into the Livefyre App.

To optimize for mobile, Livefyre limits the Comments, Live Blog, and Chat App feature set to include:

* Post
* Edit
* Flag
* Like
* Reply
* Listener Count
* Comment Count
* Inline Pending Moderation
* Hovercards
* Top Comments
* Hot Threads
* Queue Comments

In Mobile Web Apps, clicking an author's name opens hovercard information in a new page.

## Livefyre Android SDK or iOS SDK {#section_zdz_spb_11b}

Livefyre also provides two mobile SDKs: an iOS SDK, and an Android SDK. These SDKs are wrappers around our HTTP endpoints, built to provide an easier method to send and receive data. No interface is provided with these SDKs, allowing greater flexibility with how the content is displayed and used within your mobile app.

The Android and iOS SDKs support the following features for Comments, Live Blog, and Chat:

|iOS features:|Android features:|
|--- |--- |
|<ul><li> Post </li><li>Edit </li><li>Flag </li><li>Like </li><li>Reply </li><li>Hot Threads</li></ul>|<ul><li>Post </li><li>Edit </li><li>Like </li><li>Reply </li><li>Hot Threads</li></ul>|

## HTTP APIs {#section_yqb_qpb_11b}

The HTTP APIs are the group of endpoints that allows you to create conversations and content on the Livefyre platform. It also powers all Livefyre out of the box streams. While this solution requires more development time from your engineering team, it provides greater flexibility when using the Livefyre product suite, and allows for native mobile integration.

>[!IMPORTANT]
>
>**Do not** create user authentication tokens within the mobile client, because this would require that you expose your Livefyre secret network key within an unsecured app. For a more robust and secure solution, see the User Authentication Tokens section.
