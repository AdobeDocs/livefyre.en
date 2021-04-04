---
description: Livefyre uses a PUSH interface to send an external system information about changes to user permissions.
seo-description: Livefyre uses a PUSH interface to send an external system information about changes to user permissions.
seo-title: Posting User Permissions to External Systems (Optional)
solution: Experience Manager
title: Posting User Permissions to External Systems (Optional)
uuid: 9c18b20d-3b93-4666-b7de-1ec60318cf88
exl-id: 335c9ff2-e392-4310-aad2-7890c8e82eba
---
# Posting User Permissions to External Systems (Optional){#posting-user-permissions-to-external-systems-optional}

Livefyre uses a PUSH interface to send an external system information about changes to user permissions.

## Types of Users in Livefyre Studio

|User Type|Description|
|--- |--- |
|owner|This user is an owner, and can both moderate content, and assign new moderators.|
|admin|This user is a moderator, and can moderate content.|
|member|This user is allow-listed. Posted content does not pass through spam or profanity filters, and does not require approval in pre-moderated streams.|
|none|This user is a standard user, and has no special permissions.|
|outcast|This user has been banned from participating in any conversations.|

To post user permissions to external systems, you must register a URL that receives permissions data as POST requests.

For example:

```
POST https://{networkName}.quill.fyre.co/?actor_token={token}&push_affiliation_url={url}
```

|Parameter|Description|
|--- |--- |
|networkName|Your Livefyre provided network name.|
|token|Valid system token.|
|url|URL to register.|

The URL registered should accept POSTs with the following data as content-type: application/x-www-form-urlencoded.

|Parameter|Description|
|--- |--- |
|jid|JID of the user whose affiliation is changed. A JID is a string of the form `user_id@network`.|
|affiliation|Name of the permissions assigned, which must be one of the following:  `{admin | member | none | outcast | owner}`|

For additional information on updating user affiliation settings, see the [Add User Affiliation API Reference](https://api.livefyre.com/docs/apis/by-category/user-management#operation=urn:livefyre:apis:quill:operations:api:v3.0:affiliation:add:method=post).
