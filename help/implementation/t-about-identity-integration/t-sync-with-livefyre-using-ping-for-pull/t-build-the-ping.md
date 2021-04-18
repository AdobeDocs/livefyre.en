---
description: Build the ping so your page pings Livefyre when users update their profile.
title: Build the Ping
exl-id: 626c200b-eaff-483f-b1eb-7d8993fe5e7c
---
# Build the Ping{#build-the-ping}

Build the ping so your page pings Livefyre when users update their profile.

When Livefyre receives an update notification with the `networkName` and `user_id`, the system will send a Pull request to your Ping for Pull URL.

>[!NOTE]
>
>403/Not Authorized in response to your Ping indicates an invalid `lftoken` appended to the Ping request. Please ensure that the `lftoken` is for a `user_id` with network owner privileges or the system user. If you are using Livefyre libraries, use the `buildLivefyreToken` method to generate a valid system token for the request.

1. Add code to your page that pings Livefyre when users update their profile. Construct the URL this way:

   ```  

   POSThttps://{networkName}.quill.fyre.co/api/v3.0/user/{user_id}/refresh?lftoken={token}
   ```

   * **[!UICONTROL networkName:]** Your Livefyre provided network name.
   * **[!UICONTROL user_id:]** Your user’s ID.
   * **[!UICONTROL token:]** Valid system token.

1. Pull the request structure.
