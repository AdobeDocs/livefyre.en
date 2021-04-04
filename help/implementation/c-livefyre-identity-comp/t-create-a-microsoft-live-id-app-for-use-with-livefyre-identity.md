---
description: You can use Livefyre Identity with Microsoft Live Identity to allow users to use their Facebook logins to interact Apps on your site.
seo-description: You can use Livefyre Identity with Microsoft Live Identity to allow users to use their Facebook logins to interact Apps on your site.
seo-title: Create a Microsoft Live Identity App for Use with Livefyre Identity
solution: Experience Manager
title: Create a Microsoft Live Identity App for Use with Livefyre Identity
uuid: 0c13e1bc-817f-43ed-85d5-09c9e95b6234
exl-id: 7702c956-ecb5-424a-9866-d6f73d4d4bc9
---
# Create a Microsoft Live Identity App for Use with Livefyre Identity{#create-a-microsoft-live-identity-app-for-use-with-livefyre-identity}

You can use Livefyre Identity with Microsoft Live Identity to allow users to use their Facebook logins to interact Apps on your site.

To allow users to log in with their Microsoft Live Identity credentials, Livefyre requires the following Microsoft Live Identity Information:

* Client ID (Private Key)
* Client Secret (Password)

To create an Microsoft Live Identity app for use with Livefyre Identity:

1. Create or sign in to a Microsoft Live account at [https://apps.dev.microsoft.com](https://apps.dev.microsoft.com/)
1. Create a new or select an existing app for use with Livefyre Identity.
1. Click **[!UICONTROL Add Platform]**, then select Web as the platform type.
1. Make sure the **[!UICONTROL Allow Implicit Flow]** option is checked and enter the Redirect URL, using your network name instead of {network-name}: `https://identy.livefyre.com/{network-name}.fyre.co/api/v.1.0/public/profile/social/complete/mslive_fyre`.
1. Generate a new password/key pair to get the Private Key.
1. In **[!UICONTROL Livefyre Integration Settings Livefyre Identity Microsoft Live]**, switch the **[!UICONTROL Enable Microsoft Live Login]** toggle to **[!UICONTROL On]**.
1. Enter the Microsoft Live Client ID and Microsoft Live Client Secret.
1. Click **[!UICONTROL Save Settings]**.

When complete,Microsoft Live Identity’s app details page will list the app’s Client ID (Consumer Key) and Client Secret (Consumer Secret) for use in Studio’s Integration Settings page.
