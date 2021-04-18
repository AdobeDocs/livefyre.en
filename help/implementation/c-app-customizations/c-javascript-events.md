---
description: The events available to which you can bind JavaScript for conversation Apps (for example, Comments, Chat, Live Blog, Reviews, and Sidenotes).
title: JavaScript Events Definitions and Examples
exl-id: 5b865974-69aa-4d51-ac26-60f1d8a114fc
---
# JavaScript Events Definitions and Examples{#javascript-events-definitions-and-examples}

The events available to which you can bind JavaScript for conversation Apps (for example, Comments, Chat, Live Blog, Reviews, and Sidenotes).

Livefyre provides JavaScript events to track user activity in your Livefyre Apps. For example, you may wish to update the page when users like or share content to Twitter or Facebook, or when new content is posted.

Livefyre also allows you to add events to third-party analytics integrations (Adobe Analytics JS, Google Analytics, Dynamic Tag Management, etc.), to track App events. For more information, work with your third-party integration manager to supply the correct events.

To bind to these events, add the following code to the page when instantiating your App on a page. Substitute the event name for `{eventName}`:

```
Livefyre.require(['fyre.conv#3'], function(Conv) { 
   new Conv(networkConfig, [convConfig], function(widget) { 
      widget.on('{eventName}', function (data) { 
         // Do something, perhaps using data 
      }); 
   }); 
});
```

>[!NOTE]
>
>Data objects are provided for all event handlers. Example data objects follow each event.

## commentPosted {#section_qfr_51p_xz}

A user posted a comment.

* A parent of null is a new comment.
* A parent of None is a comment that has been edited.
* A number for parent is the parent ID of the reply.

```
data = { 
   authorId: "_u2012@livefyre.com" // The ID of the author of the comment  
   parent: "893549"  
      // The ID of the comment that this new comment is in reply to, else null 
   bodyHtml: "<p>42</>" // The HTML of the submitted Content 
   sharedToFacebook:true // Whether the comment was also posted to Facebook 
   sharedToTwitter:false // Whether the comment was also posted to Twitter 
   title: "demo title" // The title of the review (exists only for Reviews) 
   rating: [90] // Array of ratings for the review (exists only for Reviews) 
} 

```

## commentFlagged {#section_szy_s1p_xz}

A user flagged a comment.

```
data = { 
   targetId: "789347" // The ID of the comment that was flagged 
   type: ["disagree"] // The type of flag 
   notes: ["I don't entirely agree with this post"] // A note/reason for the flag 
}
```

## commentLiked {#section_vc1_r1p_xz}

A user liked a comment.

```
data = { 
   targetId: "245625" // The ID of the comment that was liked 
   targetAuthorId: "i_am_author@livefyre.com"  
      // The ID of the author of the comment that was liked 
} 

```

## commentShared {#section_nqb_31p_xz}

A user shared a comment from the stream. (This event does not fire when users share from the Comment editor.) This event is triggered when the Share button is clicked.

```
data = { 
   targetId: "256255" // The ID of the comment that was shared 
   sharedToFacebook:false // Whether the comment was shared to Facebook 
   sharedToTwitter:true // Whether the comment was shared to Twitter 
}
```

## commentCountUpdated {#section_qdq_f1p_xz}

The total number of visible comments in this conversation has changed (either incremented or decremented).

```
data: 34 // The total number of visible comments in the conversation (integer). 

```

## userLoggedIn {#section_yjt_vz4_xz}

A user has logged in.

```
data = { 
   avatar: "https://gravatar.com/avatar/50.jpg"  
      // Link to logged in user's avatar image 
   displayName: "NewUser" // Display name of the logged in user 
   id: "newuser@livefyre.com" // ID of the logged in user 
   isModerator:false // Boolean indicating whether logged in user is a moderator 
}
```

## userLoggedOut {#section_tsg_5z4_xz}

A user has logged out.

data is undefined.

## socialMention {#section_a1w_tz4_xz}

A user included an @mention in a comment. Returns an array of the following:

```
data = { 
   id: '111111@fb.gw.livefyre.com' // ID of the mentioned user 
   displayName: 'testUser' // Display name of mentioned user 
   message: "@testUser Wow, I can't believe it either!"  
      // Message that was sent to the particular user 
   provider: 'twitter' // Provider to which the mention was shared 
} 

```

## commentFeatured

A moderator user featured a comment. Returns an array of the following:

```
data = { 
   targetId: "134234" // The ID of the comment that was featured 
   targetAuthorId: "i_am_author@livefyre.com"  
      // The ID of the author of the comment that was featured 
}
```

## initialRenderComplete {#section_odc_4z4_xz}

The comment stream has loaded, and the initial set of content has been fetched from the server and displayed to the user.

data is undefined.

## showMore {#section_pqg_nz4_xz}

A user clicked the **[!UICONTROL Show More]** button.

data is undefined.

## userFollowed {#section_xxw_jz4_xz}

Returns true when a user clicks the **[!UICONTROL Follow]** button, and false when content is posted to the stream.

```
data = { 
   id: 'authorId@livefyre.com', 
   optIn: true 
}
```

## userUnfollowed {#section_wm1_gz4_xz}

Returns true when a user clicks the **Unfollow** button, and false when content is posted to the stream.

```
data = { 
   id: 'authorId@livefyre.com', 
   optOut: true 
}
```
