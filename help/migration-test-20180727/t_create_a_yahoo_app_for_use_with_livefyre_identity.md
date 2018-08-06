---
description: You can use Livefyre Identity with Yahoo! to allow users to use their Yahoo! logins to interact with Apps on your site.
seo-description: You can use Livefyre Identity with Yahoo! to allow users to use their Yahoo! logins to interact with Apps on your site.
seo-title: Create a Yahoo! App for Use with Livefyre Identity
solution: Experience Manager
title: Create a Yahoo! App for Use with Livefyre Identity
uuid: b387029a-10e4-4e53-b809-a523e8a79d89
index: y
internal: n
snippet: y
translate: y
---

# Create a Yahoo! App for Use with Livefyre Identity

To allow your users to log in with their Yahoo credentials, Livefyre requires the following Yahoo App information:

* Client ID (Consumer Key)
* Client Secret (Consumer Secret)
To create a Yahoo! app for use with Livefyre Identity:

>1. Go to [https://developer.yahoo.com/apps/](https://developer.yahoo.com/apps/), and sign into your Yahoo! account to create a new or select an existing app for use with Livefyre Identity.
>1. Select ** `Application Type: Web Application` **.
>1. Enter ** `Callback Domain:` ** https://identity.livefyre.com
>1. Select ** `API Permissions: Profiles (Social Directory)` ** and ** `Read Public` **.
>   When complete, Yahoo’s app details page will list the app’s Client ID (Consumer Key) and Client Secret (Consumer Secret) for use in Studio’s Integration Settings page.

>   >[!NOTE]
>   >
>   >If you enable Yahoo! login without creating a Yahoo! app, and if you leave the Client ID and Client Secret fields in Studio blank, Livefyre will use OpenID to log these users into your Livefyre Apps. OAuth and custom branding will not be available in this case.
>
