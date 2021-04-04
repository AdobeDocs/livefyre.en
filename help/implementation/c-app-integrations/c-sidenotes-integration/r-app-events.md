---
description: You can listen to events on an instance of Sidenotes.
seo-description: You can listen to events on an instance of Sidenotes.
seo-title: Sidenotes App Events
solution: Experience Manager
title: Sidenotes App Events
uuid: afca4b03-c370-41ca-aa12-45bc357517ca
exl-id: e341ca76-002d-425c-8d1a-35c3253fb254
---
# Sidenotes App Events {#sidenotes-app-events}

You can listen to events on an instance of Sidenotes.

Callbacks can be registered with the `onmethod` and unregistered with the `removeListener` method. A `once` method is available for convenience if the callback is to be called only once and then unregistered.

```
var app = Livefyre.Sidenotes(convConfig); 
   app.once('sidenotes.initialized', function () { 
     // Sidenotes initialized!  
});
```

For more information on Livefyre events, see the JavaScript Events page in the Reference section.

|Key|Description|
|--- |--- |
|sidenotes.initialized|Fired when the App is instantiated, has data, and is on the page.|
|sidenotes.commentFlagged|Fired when a comment has been flagged. Data contains: <br><ul><li>`targetId`: id of the comment that was flagged</li><li>`type`: flag type string `(offensive, off-topic, spam, disagree)`</li></ul>|
|`sidenotes.commentPosted`|Fired when a comment has been posted. Data contains: <br><ul><li> `authorId`: id of the author of the comment </li><li>`bodyHtml`: body of the comment </li><li> `parent`: id of the comment’s parent, or null</li></ul>|
|`sidenotes.commentShared`|Fired when a comment has been shared. Data contains: <br><ul><li>`targetId`: id of the comment that was shared </li><li> `sharedToFacebook`: whether the comment was shared to Facebook </li><li>`sharedToTwitter`: whether the comment was shared to Twitter</li></ul>|
|`sidenotes.commentVoted`|Fired when a comment has been voted on. Data contains: <br><ul><li>`targetId`: id of the comment that was voted on </li><li> `targetAuthorId`: id of the author whose comment was voted on</li><li> `type`: numerical vote type: 0: ‘clear’, 1: ‘upvote’, or 2: ‘downvote’</li></ul>|
|`sidenotes.userLoggedIn`|Fired when a user logs in. Data contains: <br><ul><li>`avatar`: avatar url for the user </li><li>`displayName`: display name of the user</li><li>`id`: id of the user</li><li> `isModerator`: whether the user is a moderator of the current collection</li></ul>|
|`sidenotes.userLoggedOut`|Fired when a user logs out|
