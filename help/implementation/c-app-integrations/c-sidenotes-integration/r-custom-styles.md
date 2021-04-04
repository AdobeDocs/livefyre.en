---
description: Custom styles are applied through an object injected into the Sidenotes constructor.
seo-description: Custom styles are applied through an object injected into the Sidenotes constructor.
seo-title: Sidenotes Custom Styles
title: Sidenotes Custom Styles
uuid: 0f6d7ad6-1f6a-4ed2-b86a-0d03782e591e
exl-id: 846605b7-a21e-4600-bf17-18841d2ed96d
---
# Sidenotes Custom Styles{#sidenotes-custom-styles}

Custom styles are applied through an object injected into the Sidenotes constructor.

The “keys” are object keys which represent DOM elements, while “properties” are supported CSS properties for the particular key. For example, to customize the style of the blockBtn (which is the button that launches the Sidenotes popover), one would construct an object such as:

```
var styles = { 
   'blockBtn': { 
      'fontColor': '#555', 
      'fontSize': '18px' 
   } 
}; 
new Livefyre.Sidenotes({ 
   customStyles: styles, 
      ...  
})
```

|  **Key** | **Properties** | Description  |
|---|---|---|
|  `anonymousAvatar`  | ‘height’, ‘width’  | Anonymous avatar image, to left of text area editor.  |
|  `blockBtn`  | ‘fontColor’, ‘fontSize’, ‘left’, ‘position’, ‘right’, ‘top’  | The “Launcher icon” placed next to elements specified as sidenote-able.  |
|  `blockBtnActive`  | ‘fontColor’, ‘fontSize’, ‘left’, ‘position’, ‘right’, ‘top’  | Launcher icon when in an active state.  |
|  `commentAvatar`  | ‘height’, ‘width’  | Avatar image to the left of top level notes.  |
|  `commentBody`  | ‘fontColor’, ‘fontFamily’, ‘fontSize’, ‘fontWeight’, ‘lineHeight’  | Text body of threaded notes.  |
|  `commentDisplayName`  | ‘fontColor’, ‘fontFamily’, ‘fontSize’, ‘fontWeight’, ‘lineHeight’  | Display name of user who has left a note.  |
|  `commentDownvote`  | ‘fontColor’, ‘fontSize’  | Downvote button on a note.  |
|  `commentReplyExpand`  | ‘backgroundColor’, ‘borderColor’, ‘borderWidth’, ‘fontColor’, ‘fontFamily’, ‘fontSize’, ‘fontWeight’, ‘lineHeight’  | Button for expanding threads with a large number of replies.  |
|  `commentTags`  | ‘fontColor’, ‘fontFamily’, ‘fontSize’, ‘fontWeight’, ‘lineHeight’  | Tags about a user on a note.  |
|  `commentUpvote`  | ‘fontColor’, ‘fontSize’  | Upvote button on a note.  |
|  `editorTextarea`  | ‘height’, ‘width’, ‘fontColor’, ‘fontFamily’, ‘fontSize’, ‘fontWeight’, ‘lineHeight’  | Textarea input box for leaving notes.  |
|  `mediaBlockBtn`  | ‘fontColor’, ‘fontSize’, ‘left’, ‘position’, ‘right’, ‘top’  | Media launcher icon when on top of a media item (img, video).  |
|  `mediaBlockBtnActive`  | ‘fontColor’, ‘fontSize’, ‘left’, ‘position’, ‘right’, ‘top’  | Media launcher icon in an active state.  |
|  `numSidenotes`  | ‘fontColor’, ‘fontFamily’, ‘fontSize’, ‘fontWeight’, ‘lineHeight’, ‘backgroundColor’, ‘borderColor’, ‘borderWidth’, ‘height’, ‘width’  | Clickable button that shows the number of Sidenotes in the collection.  |
|  `numSidenotesPopover`  | ‘fontColor’, ‘fontFamily’, ‘fontSize’, ‘fontWeight’, ‘lineHeight’, ‘backgroundColor’, ‘borderColor’, ‘borderWidth’, ‘height’, ‘width’  | Popover with a brief explanation of Sidenotes for the user.  |
|  `popover`  | ‘backgroundColor’  | Popover that is brought up when launcher icon invoked.  |
|  `popoverArrowLeft`  | ‘backgroundImage’, ‘height’, ‘left’, ‘right’, ‘top’, ‘width’  | Left arrow element on the popover that points to the DOM element containing a launcher icon.  |
|  `popoverArrorRight`  | ‘backgroundImage’, ‘height’, ‘left’, ‘right’, ‘top’, ‘width’  | Right arrow element on the popover that points to the DOM element containing a launcher icon.  |
|  `popoverArrowTop`  | ‘backgroundImage’, ‘height’, ‘left’, ‘right’, ‘top’, ‘width’  | Top arrow element on the popover that points to the DOM element containing a launcher icon.  |
|  `replyAvatar`  | ‘height’, ‘width’  | Avatar image to the left of reply level notes.  |
|  `streamPoweredBy`  | ‘backgroundColor’, ‘borderColor’, ‘lineHeight’  | “Powered by” footer on the popover.  |
|  `streamQueueButton`  | ‘backgroundColor’, ‘borderColor’, ‘borderWidth’, ‘fontColor’, ‘fontFamily’, ‘fontSize’, ‘fontWeight’, ‘lineHeight’  | Button to indicate when new notes stream into an open popover.  |
|  `userAvatar`  | ‘height’, ‘width’  | Authenticated user’s avatar image, to the left of the text area editor.  |
