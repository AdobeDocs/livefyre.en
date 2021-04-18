---
description: Register the URL endpoint so Livefyre can use the URL to pull updated profile information.
title: Register the Endpoint with Studio
exl-id: 2910a13a-ae88-41d7-ba7c-88d7a1dbe445
---
# Register the Endpoint with Studio{#register-the-endpoint-with-studio}

Register the URL endpoint so Livefyre can use the URL to pull updated profile information.

Register the Ping for Pull URL only once per network. Once set, this value should not change unless the endpoint for fetching user profile data from your user management system changes.

1. Use Studio to register this URL endpoint with Livefyre.
1. Register the URL from which Livefyre will fetch updated user profile information, go to **[!UICONTROL Studio > Settings > Integration Settings > Remote Profiles]**, and enter it in the **[!UICONTROL Ping for Pull URL]** field.

   For example, the URL can look like: `https://example.yoursite.com/some_path/?id={id}`
