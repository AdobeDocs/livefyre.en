---
description: Build the Ping for Pull response to transmit updated user information to Livefyre.
title: Build the Ping for Pull Response
exl-id: 81c398fd-2acb-4e39-a2b3-c96921b1192b
---
# Build the Ping for Pull Response{#build-the-ping-for-pull-response}

Build the Ping for Pull response to transmit updated user information to Livefyre.

|Type|Property|Description|
|--- |--- |--- |
|String *required*|id|The user ID of the user in your profile system. This must be unique across all users in your Network, and must never change.|
|String *required*|display_name|The display name of the user. This will be rendered with Livefyre Content posted by the user.|
|Object *optional, but recommended*|name|Strings to define the user’s formatted, first, middle, and last names.|
|String *optional, but recommended*|email|User’s email address. Used to send email notifications.|
|String *optional, but recommended*|image_url|URL to an avatar to display for the user. Livefyre scales uploaded images to 100×100, 75×75, or 50×50 pixels, as appropriate. For best results, users should upload a square image, at 100×100 pixels. To ensure the avatar image is updated in Livefyre, modify the image_url for each image update so Ping for Pull detects that the image was changed. For example, attach a timestamp to the filename or increment the image changes. Note:  All URLs must be fully qualified and accessible.|
|String *optional, but recommended*|profile_url|URL to the user’s profile page on your site.|
|String *optional, but recommended*|settings_url|URL to a page where users may configure the user’s profile settings for your site.|
|Array *optional, but recommended*|tags|Used to assign users to user groups. Tags may include 1-63 alphanumeric and underscore characters.|
|Boolean *optional, but recommended*|autofollow_conversations|Defines whether a user wishes to automatically follow a Collection after posting to it. When following a Collection, users receive email notifications when other users participate. May be true or false. Defaults to true.|
|Object *optional, but recommended*|email_notifications|Defines the frequency of available Livefyre email notifications. Different frequencies may be set for each notification type. By default, no notifications will be sent. <br><ul><li> immediately issues notifications immediately upon the listed event. </li><li>often issues notifications in batches. </li><li> never will not send email notification for the activity. </li><li>*comments*: Defines when notifications are sent when other users post content into Collections that this user is following. </li><li>*replies*: Defines when notifications are sent when another user replies to this user’s content.</li><li>*likes*: Defines when notifications are sent when another user likes this user’s content.</li><li>*moderator_comments*: Defines when notifications are sent to moderators when users post content to any Collection in the Network.</li><li>*moderator_flags*: Defines when notifications are sent to moderators when other users flag content in any Collection in the Network.</li></ul>|
|String *optional*|location|A user-submitted location.|
|String *optional*|bio|A user-submitted autobiography.|
|Array *optional*|websites|An array of user-submitted sites. Max = 2.|
|Object *optional*|display_rules|Defines which profile properties are publicly visible to other users. Each available parameter takes Boolean input true or false. Available parameters:  <br><ul><li>bio </li><li> location</li><li>  gender </li><li>nameimage </li><li> remote_profile_url</li></ul>|
|Boolean *optional*|moderator|Defines whether the user has moderator privileges across the network.|
|Boolean *optional*|gravatar_disabled|Defines whether to disable Livefyre’s use of a gravatar if no  image_url is provided.|

## Example Response {#section_uxt_3dd_mz}

```
{
 "id": "1234567890",
 "display_name": "Bob Dole",
 "name": {
   "formatted": "Bob Joseph Dole",
   "first": "Bob",
   "middle": "Joseph",
   "last": "Dole"
 },
   "email": "bob@dole.com",
   "image_url": "https://dole.com/images/bob.jpg",
   "profile_url": "https://site.com/bobdole",
   "settings_url":"https://site.com/settings",
   "tags": ["bob", "dole"],
   "autofollow_conversations": "true",
   "email_notifications": {
      "comments": "never",
      "replies": "immediately",
      "likes": "often",
      "moderator_comments": "immediately",
      "moderator_flags": "immediately" 
 },
  "location": "Washington D.C., USA",
  "bio": "Bob Dole speaks in the third person",
  "websites": ["https://dole.com/blog/", "https://bobdolerocks.com"],
  "display_rules": {
      "bio": "false",
      "location": "false",
      "gender": "false",
      "name": "false",
      "image": "false",
      "remote_profile_url": "false"
  },
  "moderator": "true",
  "gravatar_disabled": "false"
}
```
