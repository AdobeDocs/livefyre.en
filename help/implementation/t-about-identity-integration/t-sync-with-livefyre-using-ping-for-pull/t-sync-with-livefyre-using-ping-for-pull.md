---
description: Use Ping for Pull to keep Livefyre in sync with your user management system.
seo-description: Use Ping for Pull to keep Livefyre in sync with your user management system.
seo-title: Sync with Livefyre Using Ping for Pull
solution: Experience Manager
title: Sync with Livefyre Using Ping for Pull
uuid: 7b059064-1cca-46d7-8055-dfe59f493ac1
exl-id: 01b5851d-9dc0-44dc-9c0d-0c467502450d
---
# Sync with Livefyre Using Ping for Pull{#sync-with-livefyre-using-ping-for-pull}

Use Ping for Pull to keep Livefyre in sync with your user management system.

In general, you ***Ping*** Livefyre any time a user of your website/app updates their profile (display name, avatar, etc.), and Livefyre ***Pulls*** that user’s updated profile.

![](assets/Ping-for-Pull.png)

Ping for Pull Sequence:

1. Customer sends Ping request to Livefyre (including the User to be updated).
1. Livefyre confirms receipt of Ping with HTTP 200/Success.
1. Livefyre processes Pull request.
1. Livefyre queues Pull request.
1. Livefyre executes Pull request to endpoint to capture updated user info.
1. Customer receives Pull response, and validates.
1. Livefyre updates Remote Profiles with the external profile info included in the Pull endpoint.

Ping Livefyre whenever a user updates their profile information. While Ping for Pull completion time can vary depending on network load, it will update user information in between 1 and 10 minutes. Updated profile changes will display first within Livefyre Studio > Users.

Updated Profile information will appear in your Livefyre Apps after two events:

* A user logs out, then logs back into the App. Display name values in the userAuthToken take precedence over Ping for Pull updates. A user logout/login will refresh the token to update the session.

  To generate new userAuthTokens when profile information is updated, use the SSO authDelegate to log your user out then in again in the background.

* A bootstrap update to the Collection will bring in the updated information (at most every 5-10 minutes).

To implement Ping for Pull for your User Profile system:

1. [Build the Pull endpoint](#t_build_the_pull_endpoint).

   >[!NOTE]
   >
   >The Livefyre library includes a syncUser method for keeping your user profiles up to date. Skip the next two steps if you use the Livefyre library.

1. [Register the Pull endpoint in Studio](#register_the_endpoint_with_studio).
1. [Build the Ping](#t_build_the_ping).
1. [Build the Ping for Pull Response].(#reference_n3x_pzb_mz)
