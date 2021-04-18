---
description: Release Notes for the November 15, 2018 release.
title: Release Notes
exl-id: 3f904022-b770-4f35-a3b0-790e15748763
---
# Release Notes{#release-notes}

Release Notes for the November 15, 2018 release.

## New Features {#section_syx_mdt_wcb}

The following new features were released in the production version of this release:

* **Updates to Instagram search and stream.** You can use an *Instagram business account* to:

  * Perform an Instagram social search by user (user must be an Instagram business account also).

  * Create Instagram streams from a specific Instagram user account (the account must also be a business account), including your own.

  * Request rights for assets from Instagram using a partially-automated workflow.

  * For information on what type of Instagram accounts you need to set up and requesting rights from Instagram, see [About Instagram Accounts](/help/using/c-users-creating-accounts-with-studio-access/t-configure-social-accout-instagram/c-about-instagram-accounts.md).

* **Automatic monitoring of usage rights request responses for business account-based searches.** For business accounts-based searches only--the ability to automatically monitor responses to rights requests and update the activity history in Livefyre is available.

For more information on how to request rights for Instagram accounts, see [Send Instagram Rights Request Manually](/help/using/c-how-requesting-rights-works/c-send-instagram-manual-rights-request.md) and [Send a Partially-Automated Instagram Rights Request](/help/using/c-how-requesting-rights-works/c-send-an-instagram-rights-request-from-the-library.md).

* **Adobe Target integration.** Added integration with Adobe Target allowing you to share Livefyre Apps directly to your Adobe Target Offers Library. For more information about using Livefyre with Adobe Target, see [Target documentation](hhttps://docs.adobe.com/content/help/en/livefyre/using/library/livefyre-target.html).

## Issues {#section_ehw_ndt_wcb}

The issues in the following tables were resolved in this release.

### Production Release

|Issue Type|Component|Release Note|
|--- |--- |--- |
|Issue|AppService: Livefyre Identity|Fixed an issue where clicking on [!UICONTROL Reset to Default] did not reset the logo under Login Modal in Studio > Integration Settings > Livefyre Identity to the default image.|
|Issue|Library|Fixed an issue where a video uploaded to the Library, then viewed in asset detail did not display correctly.|
|Issue|Streams|Fixed an issue that prevented products from displaying in a stream rule.|
|Issue|Streams|Fixed an issue where product tags were not available for a stream rule.|
|Enhancement|Studio|Fixed an issue where product ID was not showing up in Livefyre Studio.|
|Issue|Studio: ModQ|Fixed an issue where deleted content still displayed in ModQ after it was deleted.|

### UAT Release

|  **Issue Type** | **Component** | **Release Note** |
|---|---|---|
| Issue | Social Component: Carousel | Fixed an issue where the Share link did not respond and copy the URL as expected in IE11 and Mozilla Firefox.|
