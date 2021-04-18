---
description: You can allow-list your video domain.
title: userPrivacyVideoWhitelist

---

# userPrivacyVideoWhitelist{#userprivacyvideowhitelist}

If you use your own custom videos and players as part of the videos that display in a Livefyre visualization App, you can allow-list your video domain. Allow-listing your video domain removes the video mask for your custom videos and players.

>[!NOTE]
>
>Use specific paths to ensure only the videos that are safe are allow-listed. If you put a broad path (for example, sampledomain.com), you may allow-list unsafe videos.

* Add `userPrivacyVideoWhitelist` after `userPrivacyOptOut`. You can add all the Livefyre privacy flags all at once as part of one Livefyre object.
* `userPrivacyVideoWhitelist` only applies to content that is not embedded from social media.

In the following example, videos displaying in Apps with the `sampledomain.com/cdn/videos` path are allow-listed:

```
userPrivacyVideoWhitelist: ["sampledomain.com/cdn/videos"]
```
