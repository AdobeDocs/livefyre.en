---
description: Customizing the text strings for Livefyre Sidenotes
title: Sidenotes Text Strings
exl-id: 132a7c8d-10e1-419c-9d79-a40553e70785
---
# Sidenotes Text Strings{#sidenotes-text-strings}

Customizing the text strings for Livefyre Sidenotes

This page lists and describes all strings available for customization in Sidenotes apps. For information on strings available for the core Livefyre apps, please see String Customizations.

Implementation
Auth
Stream Info
Author / Content Info
User Actions
Post Functions
Moderator Interface
Errors

## Implementation {#section_wp2_ql4_xz}

To implement this feature, pass in a 1-1 object mapping of the strings you wish to override to the Javascript configuration object. If you don’t provide a field, then the default text will be used.

Example:

```
var customStrings = { 
   postAsButton: "New Post As Text", 
   postEditButton: "New Post Edit Text" 
}; 
networkConfig["strings"] = customStrings; fyre.conv.load( 
   networkConfig, 
   [convConfig], 
   function(){} 
);
```

## Authentication {#section_pqf_3l4_xz}

Strings available for the Authentication process, and from the authenticated user menus.

|  Element  | Key  | Default Text  |
|---|---|---|
| Auth menu strings | menuAuthSignInBtn  | Sign in  |
|  | menuAuthSignedInMsg  | You must be signed in to {action}  |
|  | menuUserEditProfile  | Edit Profile  |
|  | menuUserAdmin  | Admin Console  |
|  | menuUserLogout  | Sign Out  |
|  | menuUserBackBtn  | All  |

## Stream Info {#section_wpy_gl4_xz}

Strings available for content stream information and display.

|  Element  | Key  | Default Text  |
|---|---|---|
| Info menu options | menuInfoCopyright  | &copy; Livefyre, Inc. 2014  |
|  | menuInfoHelp  | Help  |
|  | menuInfoLivefyreLink  | Visit Livefyre.com  |

## Author / Content Info {#section_dhb_gl4_xz}

Stings available for author and individual content information.

|  Element  | Key  | Default Text  |
|---|---|---|
|  | commentModeratorTag  | Mod  |
|  | commentPendingTag  | Pending  |
|  | commentReadMoreLink  | Read More  |
|  | commentReplyLink  | See {number} replies  |
|  | commentReplyLinkSing  | See reply  |
|  | commentVoteCount  | votes  |
|  | commentVoteCountSing  | vote  |
|  | datetimeMinutePrefix  | m  |
|  | datetimeMonths  |An array. Default =`[‘January’, ‘February’, ‘March’, ‘April’, ‘May’, ‘June’, ‘July’, ‘August’, ‘September’, ‘October’, ‘November’, ‘December’]`  |
|  | questionExplanation  | You can now read and write comments directly on sentences, paragraphs, images and quotes.<br><br><span class=”lf-highlight-text”>Highlight text</span> and click the <span class=”fycon-write”></span> icon or click the <span class=”fycon-action-view”></span> icon at the end of each paragraph.  |
|  | questionMockText  | What is “familiarly known” is not properly known, just for the reason that it is “familiar”.  |
|  | questionTitle  | What is a Sidenote?  |

## User Actions {#section_qxd_fl4_xz}

Strings available for user actions: flagging, sharing, and liking existing content.

|  Element  | Key  | Default Text  |
|---|---|---|
| Reply menu options | menuRepliesViewTitle  | Details  |
|  | menuRepliesViewReply  | Reply to Conversation  |
| Share menu options | menuShareOptionFacebook  | Facebook  |
|  | menuShareOptionTwitter  | Twitter  |
|  | menuShareTitle  | Share  |
| Flag menu options | menuFlagOptionDisagree  | Disagree  |
|  | menuFlagOptionOffensive  | Offensive  |
|  | menuFlagOptionOffTopic  | Off Topic  |
|  | menuFlagOptionSpam  | Spam  |
|  | menuFlagTitle  | Flag as…  |
|  | facebookShareCaption  | Sidenotes on “{title}”  |
| Mobile user options | sliderCommentTally  | of  |
|  | sliderInviteRead  | Read  |
|  | sliderInviteWrite  | Write  |
|  | sliderLoading  | Loading…  |
|  | sliderWriteText  | What do you think? Tap to write.  |

## Post Functions {#section_xzf_2l4_xz}

Strings available for users posting content.

|  Element  | Key  | Default Text  |
|---|---|---|
|  | editorEditBtn  | Save  |
|  | editorEditPosting  | Saving…  |
|  | editorEditReplyTitle  | Edit Reply  |
|  | editorEditTitle  | Edit Sidenote  |
|  | editorPlaceholder  | What do you think?  |
|  | editorPostBtn  | Post Sidenote  |
|  | editorPostBtnMobile  | Post  |
|  | editorPosting  | Posting…  |
|  | editorReplyBtn  | Post Reply  |
|  | editorReplyTitle  | Write Reply  |
|  | editorTitle  | Write Sidenote  |
|  | emptyImageBlockTxt  | What do you think?  |
|  | emptyTextBlockTxt  | +  |
|  | replyBtn  | Reply  |
|  | threadReplyBtn  | Reply to Conversation  |
| Delete menu options | menuConfirmAccept  | Yes, {action}  |
|  | menuConfirmCancel  | Cancel  |
|  | menuConfirmTitle  | Are you sure?  |
| Etc menu options | menuEtcOptionApprove  | Approve  |
|  | menuEtcOptionDelete  | Delete  |
|  | menuEtcOptionEdit  | Edit  |
|  | menuEtcOptionFlag  | Flag  |
|  | menuEtcOptionShare  | Share  |
|  | menuEtcPostedAt  | Posted on {date}  |
|  | menuEtcTitle  | More  |

## Moderator Interface {#section_o5f_dl4_xz}

Strings available to the user-authenticated moderator interface.

|  Element  | Key  | Default Text  |
|---|---|---|
| Confirmation messages from the More menu | notificationApproved  | Approved  |
|  | notificationDeleted  | Deleted  |
|  | notificationFlagged  | Flagged  |

## Errors {#section_gtk_cl4_xz}

Strings available for general error messages.

|  Element  | Key  | Default Text  |
|---|---|---|
|  | errorConnection  | Uh-oh. You don’t seem to have a good connection.  |
|  | errorDuplicate  | We like your note too, but you can’t post it twice.  |
|  | errorGeneral  | An error has occurred. Please try again.  |
|  | errorServer  | Something went wrong with our server. Try that again?  |
