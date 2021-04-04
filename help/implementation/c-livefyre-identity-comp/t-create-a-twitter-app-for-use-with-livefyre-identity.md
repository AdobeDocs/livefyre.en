---
description: You can use Livefyre Identity with Twitter to allow users to use their Twitter logins to interact Apps on your site.
seo-description: You can use Livefyre Identity with Twitter to allow users to use their Twitter logins to interact Apps on your site.
seo-title: Create a Twitter App for Use with Livefyre Identity
solution: Experience Manager
title: Create a Twitter App for Use with Livefyre Identity
uuid: 841cce7c-618d-4154-85a3-1de96d04bb69
exl-id: 4f2b919f-fe5d-49a3-8432-04ffb3d68ce4
---
# Create a Twitter App for Use with Livefyre Identity{#create-a-twitter-app-for-use-with-livefyre-identity}

You can use Livefyre Identity with Twitter to allow users to use their Twitter logins to interact Apps on your site.

To enable Twitter login, Livefyre requires the following Twitter app information:

* Consumer Key (API Key)
* Consumer Secret (API Secret)

To create a Twitter App for use with Livefyre Identity:

1. Go to [https://apps.twitter.com/](https://apps.twitter.com/), and sign into your Twitter account to create a new or select an existing app for use with Livefyre Identity.
1. From the Settings page for the app:

    * Enter **[!UICONTROL Callback URL:]** `https://identity.livefyre.com/{networkName}.fyre.co/api/v1.0/public/profile/social/complete/twitter_fyre` (where **{networkName}** is your Livefyre provided network name. For example:** [!UICONTROL labs]** in **[!UICONTROL `labs.fyre.co`]**.)
    * Deselect **[!UICONTROL Enable Callback Locking]**.
    * Select **[!UICONTROL Allow this application to be used to Sign in with Twitter]**.

1. From the **[!UICONTROL Permissions]** tab, select **[!UICONTROL Access: Read only]**.

When complete, Twitter’s Application Management > Keys and Access Tokens page will list the app’s Consumer Key (API Key) and Consumer Secret (API Secret) for use in Studio’s Integration Settings page.
