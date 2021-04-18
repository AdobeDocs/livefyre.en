---
description: Use Javascript events to listen for events that occur in a Media Wall and send them to the analytics tool of your choice.
title: Javascript Events for Media Wall
exl-id: 3fe76467-65e2-4f8b-bd75-5a2ffc3e7e15
---
# Javascript Events for Media Wall{#javascript-events-for-media-wall}

Use Javascript events to listen for events that occur in a Media Wall and send them to the analytics tool of your choice.

Livefyre provides JavaScript events to track user activity in your Livefyre Apps. For example, you may wish to update the page when users like or share content to Twitter or Facebook, or when new content is posted.

Here is an example of how to receive the events. Replace `console.log` with your code to map and send the event to your analytics integration (Dynamic Tag Management, Adobe Analytics JS, Google Analytics, etc.):

```
document.body.addEventListener('insights', function (data) { 
 console.log('Received:', data.detail.type, data); 
});
```

List of supported Media Wall events:

## Media Wall Events

|  Event  | Definition  |
|---|---|
|  `Init`  | When a Media Wall is included on a page.  |
|  `Load`  | When the Media Wall was loaded on a page regardless of position.  |
|  `PostButtonClick`  | When a user clicks on an Upload Button on a Media Wall.  |
|  `RequestMore`  | When user loads more content in a Media Wall.  |
|  `TwitterReplyClick`  | When a user clicks the Twitter Reply button from the Media Wall.  |
|  `TwitterRetweetClick`  | When a user clicks the Twitter Retweet button from the Media Wall.  |
|  `TwitterLikeClick`  | When a user clicks the Twitter Like/Favorite button from the Media Wall.  |
|  `ModalView`  | When user clicks to view Media Wall content in a larger modal window.  |
|  `Like`  | When a user clicks the Like button from the Media Wall.  |
|  `ShareButtonClick`  | Any time a user clicks on the share button on a Media Wall card.  |
|  `ShareURL`  | When Share to URL text area is selected/copied from the Media Wall.  |
|  `ShareFacebook`  | When Share to Facebook is clicked from the Media Wall.  |
|  `ShareTwitter`  | When Share to Twitter is clicked from the Media Wall.  |
