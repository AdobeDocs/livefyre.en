---
description: Add a user tag to an account to add a User to a group.
seo-description: Add a user tag to an account to add a User to a group.
seo-title: Adding Users to Groups
solution: Experience Manager
title: Adding Users to Groups
uuid: 3633f2df-8d60-4cdd-b9a2-3807218c74a0
exl-id: 6e799c77-e815-40c2-ae06-bbd076df9fe7
---
# Adding Users to Groups{#adding-users-to-groups}

Add a user tag to an account to add a User to a group.

User Tags may be implemented for both proprietary and enterprise profile systems, and may be added to accounts by several means:

* Creating Owners and Moderators through Studio assigns the ‘Moderator’ User Tag to the account.
* Creating user groups, and adding users to them through Studio, automatically applies User Tags with the name of the group to the selected users.
* User Tags may be also applied directly to Accounts using the [Add User Tag HTTP](https://api.livefyre.com/docs#add-user-tag) call, or Ping for Pull.

>[!NOTE]
>
>Both API methods, the HTTP Add User Tag call and the Ping for Pull method, will overwrite any tags previously assigned to the Account through other means. Therefore, please select one method, and use it consistently throughout your process.

## Add a user to a Group from the Users page in Studio {#section_qgq_nbw_xz}

* Click **[!UICONTROL Add Group]** or the group label below any username to open the groups menu.
* Scroll through the list and find the group to which you wish to add the user. You can enter a group name in the **[!UICONTROL Search]** box at the top of the dropdown.
* Click the checkbox next to the group(s) to which the user should be added, and hit return.

The user’s profile will display either the name of the group (if the user is only in one group) or the number of groups to which the user belongs.

## Add a user to a group using the Add User Tag call {#section_kn3_gbw_xz}

Pass the user’s LFToken and your selected tag name in with the POST request

For example:

```
curl -XPOST -d 'tag_name=tag&lftoken=eyJhbGciOiAiA_TOKENcGlyZXMiOiAxMzU3OTY3NTAxLjIzn0.KoyXUVCavt-rdvkVXm2qzQTyMAOSp-crQA1uL1ht9WU' 'https://labs.quill.fyre.co/api/v3.0/author/system@`labs.fyre.co`/tag/'
```


For more information, see API Reference > [Add User Tag](https://api.livefyre.com/docs/apis/by-category/user-management#operation=urn:livefyre:apis:quill:operations:api:v3.0:author:tags:method=post).

## Add a user to a Group using Ping for Pull {#section_kyj_11w_xz}

Use the tags array to assign users to user groups. (Tags may include 1-63 alphanumeric and underscore characters.)

For example:

```
"tags": ["moderator", "brand_advocate"],

```

## Add a user to a Group using Remote Profiles {#section_uyn_scv_xz}

Add user tags to the Remote Profile, used to sync user data between your custom profile system and Livefyre, for the specific users.
