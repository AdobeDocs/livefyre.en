---
description: Add the userPrivacyOptOut flag to the page to allow a site visitor to opt out of this tracking.
seo-description: Add the userPrivacyOptOut flag to the page to allow a site visitor to opt out of this tracking.
seo-title: userPrivacyOptOut
title: userPrivacyOptOut
uuid: a043c50e-0a02-4c83-bbce-54b9b51316a5
exl-id: 1e935e69-60af-4151-905c-93a1cccbeb49
---
# userPrivacyOptOut{#userprivacyoptout}

Add the `userPrivacyOptOut` flag to the page to allow a site visitor to opt out of this tracking.

Livefyre provides JavaScript events to track user activity in your Livefyre Apps.

If you embed Livefyre Apps and a visitor does not consent to tracking, you can dynamically configure Livefyre to disable functionality to ensure the visitor’s privacy.
  
When configured, Livefyre will:

* Disable authentication support in Apps.
* Disable Livecount and event generation
* Delete existing cookies created by any Apps that are on the page
* Proxy media with images from third party domains to prevent third parties from creating cookies
* Enable video mask click-through for third party videos that require an additional click to view

## Configure a Page for Opt-Out

Integrations embedding Livefyre Apps can configure Livefyre when a site visitor has not granted consent using a single JavaScript variable.

Instructions:

1. Add the `userPrivacyOptOut` flag to the page before the `Livefyre.js` JavaScript:

   ```
   window.Livefyre = {userPrivacyOptOut: true};
   ```

1. Add `Livefyre.js` to the page anywhere after `userPrivacyOptOut`.

   Livefyre Apps instantiate with the elevated privacy settings.

   >[!NOTE]
   >
   >Do not change the value of `userPrivacyOptOut` once Livefyre Apps have loaded.

Ensure that your consent workflow sets the `userPrivacyOptOut` to true if a site visitor chooses to opt out.
