---
title: Sidenotes Custom Strings
description: Sidenotes Custom Strings
exl-id: b5e2c18b-5b98-45ff-aa89-dd92a02949a9
---
# Sidenotes Custom Strings{#sidenotes-custom-strings}

Custom strings are applied through an object injected into the Sidenotes constructor, and override default strings used through the application. These may be used to customize any part of the language to fit your style or language specifications. Strings will automatically merge with defaults.

```
var customStrings = { 
   'menuBackBtn': 'return' }; 
new Livefyre.Sidenotes({ 
   strings: customStrings, 
   ...  
});
```

|  Key  | Default  |
|---|---|
|  appName  | Sidenotes  |
|  commentModeratorTag  | Mod  |
|  commentPendingTag  | Pending  |
|  commentReadMoreLink  | Read More  |
|  commentReplyLink  | See {number} replies  |
|  commentReplyLinkSing  | See reply  |
|  commentVoteCount  | votes  |
|  commentVoteCountSing  | vote  |
|  editorPlaceholder  | What do you think?  |
|  editorPostBtn  | Post Sidenote  |
|  editorPostBtnMobile  | Post  |
|  editorPosting  | Posting…  |
|  editorReplyBtn  | Post Reply  |
|  editorReplyTitle  | Write Reply  |
|  editorTitle  | Write Note  |
|  emptyImageBlockTxt  | What do you think?  |
|  emptyTextBlockTxt  | +  |
|  errorConnection  | Uh-oh. You don’t seem to have a good connection.  |
|  errorDuplicate  | We like your note too, but you can’t post it twice.  |
|  errorGeneral  | An error has occurred. Please try again.  |
|  errorServer  | Something went wrong with our server. Try that again?  |
|  facebookShareCaption  | SideNotes on “{title}”  |
|  menuAuthSignedInMsg  | You must be signed in to {action}  |
|  menuAuthSignInBtn  | Sign in  |
|  menuBackBtn  | Back  |
|  menuConfirmAccept  | Yes, {action}  |
|  menuConfirmCancel  | Cancel  |
|  menuConfirmTitle  | Are you sure?  |
|  menuEtcOptionApprove  | Approve  |
|  menuEtcOptionDelete  | Delete  |
|  menuEtcOptionEdit  | Edit  |
|  menuEtcOptionFlag  | Flag  |
|  menuEtcOptionShare  | Share  |
|  menuEtcPostedAt  | Posted on {date}  |
|  menuEtcTitle | More  |
|  menuFlagOptionDisagree | Disagree  |
|  menuFlagOptionOffensive | Offensive  |
|  menuFlagOptionOffTopic | Off Topic  |
|  menuFlagOptionSpam | Spam  |
|  menuFlagTitle | Flag as…  |
|  menuInfoCopyright | © Livefyre, Inc. 2014  |
|  menuInfoHelp | Help  |
|  menuInfoLivefyreLink | Visit Livefyre.com  |
|  menuRepliesViewReply | Reply to Conversation  |
|  menuRepliesViewTitle | Details  |
|  menuShareOptionFacebook | Facebook  |
|  menuShareOptionLink | Copy Permalink  |
|  menuShareOptionLinkComplete | Copied  |
|  menuShareOptionLinkFailed  | Copy Failed  |
|  menuShareOptionTwitter | Twitter  |
|  menuShareTitle | Share  |
|  notificationApproved | Approved  |
|  notificationDeleted | Deleted  |
|  notificationFlagged | Flagged  |
|  permalinkBackBtn | All  |
|  permalinkTitle | Permalink  |
|  questionExplanation | You can now read and write comments directly on sentences, paragraphs, images and quotes.<br><br>Highlight text and click the ”fycon-write” icon or click the ”fycon-action-view” icon at the end of each paragraph. |
|  questionMockText | What is “familiarly known” is not properly known, just for the reason that it is “familiar”.  |
|  questionTitle | What is a Sidenote?  |
|  queuedCommentsPlural | {number} New Sidenotes  |
|  queuedCommentsSingular | 1 New Sidenote  |
|  queuedRepliesPlural | {number} New Replies  |
|  queuedRepliesSingular  | 1 New Reply  |
|  replyBtn | Reply  |
|  signInToPost | Sign in to write a sidenote  |
|  sliderCommentTally | of  |
|  sliderInviteRead | Read  |
|  sliderInviteWrite | Write  |
|  sliderWriteText | What do you think? Tap to write  |
|  threadCollapseBtn | Collapse  |
|  threadExpandBtnPlural | Expand {number} Replies  |
|  threadExpandBtnSingular | Expand 1 Reply  |
|  threadReplyBtn | Reply to Conversation  |
