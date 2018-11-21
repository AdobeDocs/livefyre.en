---
description: Translation Sets allow you to specify alternate language for Apps.
seo-description: Translation Sets allow you to specify alternate language for Apps.
seo-title: Translation Sets
solution: Experience Manager
title: Translation Sets
uuid: 683afb89-4b3d-409d-ad07-6d769b28ad3e
index: y
internal: n
snippet: y
---

# Translation Sets{#translation-sets}

Translation Sets allow you to specify alternate language for Apps.

## Translation Sets {#c_translation_sets}

Translation Sets allow you to specify alternate language for Apps.

<!-- 

c_translation_sets.dita

 -->

Use translation settings to localize Apps in various languages or to specify alternate text for several Apps from one location in Studio. For example, you can ensure all Spanish-language sites use Spanish language for all App fields. You can also modify the text so that all fields match the voice and feel of your site or network.

You can specify translation settings for all Apps, except Storify 2. For more information about what fields you can localize, see [Localize Strings](c-translation-sets/c-localize-strings.md#c_localize_strings).

Comments, Live Blog, and Chat share the same set of strings within a translation set.

Specify a translation set for a network, site, app, or using an API.

The translation sets at different levels override each other following this pattern:

* API translation set overrides any translation sets at any level (App, network, and site)
* App translation set overrides network-level and site-level translation sets. 
* Site-level translation sets override network-level translation sets.

## <draft-comment author="ind14750" otherprops="merge"> c_review_text_strings.dita </draft-comment>Review Text Strings {#c_review_text_strings}

Customizing the text strings for Livefyre Reviews. 

This page lists and describes the strings available for customization in Review apps. The strings listed here are in addition to and overrides for the default strings for Livefyre core apps, listed in String Customizations. Where duplicates are listed, the strings listed in these tables are the default for Reviews apps.

* Implementation
* Review / Rating Interface
* Stream Info
* Author / Content Info
* User Actions
* Post Functions
* Errors

## Implementation {#section_vsy_1k4_xz}

To implement this feature, pass in a 1-1 object mapping of the strings you wish to override to the Javascript configuration object. If you don’t provide a field, the default text will be used.

Example:

```
var customStrings = { 
   postAsButton: "New Post As Text", 
   postEditButton: "New Post Edit Text" }; 
networkConfig["strings"] = customStrings; fyre.conv.load( 
   networkConfig, 
   [convConfig], 
   function(){} 
);
```

## Review / Rating Interface {#section_iyv_zj4_xz}

Strings available for the Review and Rating user interface.

<table id="table_jrv_snl_wz"> 
 <thead> 
  <tr> 
   <th class="entry"> Element </th> 
   <th class="entry"> Key </th> 
   <th class="entry"> Default Text </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colspan="2"> <i>Buttons</i> </td> 
   <td></td> 
  </tr> 
  <tr> 
   <td></td> 
   <td> editReviewBtn </td> 
   <td> Edit review </td> 
  </tr> 
  <tr> 
   <td></td> 
   <td> reviewBtn </td> 
   <td> <a href="https://d.pr/i/QscA" format="html" scope="external"> Write review </a> </td> 
  </tr> 
  <tr> 
   <td></td> 
   <td> reviewsClosed </td> 
   <td> <a href="https://d.pr/i/zr7M" format="html" scope="external"> Reviews Closed </a> </td> 
  </tr> 
  <tr> 
   <td></td> 
   <td> showReviewBtn </td> 
   <td> <a href="https://d.pr/i/onxU" format="html" scope="external"> Show review </a> </td> 
  </tr> 
  <tr> 
   <td></td> 
   <td> follow </td> 
   <td> I’m interested </td> 
  </tr> 
  <tr> 
   <td></td> 
   <td> shareText </td> 
   <td> I just wrote a review. Check it out! </td> 
  </tr> 
  <tr> 
   <td colspan="2"> <i>Rating tooltips</i> </td> 
   <td></td> 
  </tr> 
  <tr> 
   <td></td> 
   <td> ratingValues </td> 
   <td> <i>An array. Default = </i>[‘Poor’, ‘Poor’, ‘Fair’, ‘Fair’, ‘Average’, ‘Average’, ‘Good’, ‘Good’, ‘Excellent’, ‘Excellent’]; 
    <ul id="ul_krv_snl_wz"> 
     <li><b>Note: </b>Values in the array must be duplicated to assign both the left and the right half of each star the same name.</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colspan="2"> <i>Rating subparts</i> </td> 
   <td></td> 
  </tr> 
  <tr> 
   <td></td> 
   <td> ratingSubpartPlaceholders </td> 
   <td> <i>An array. Default = </i>[] </td> 
  </tr> 
  <tr> 
   <td></td> 
   <td> ratingSubpartTitles </td> 
   <td> <i>An array. Default = </i>[] </td> 
  </tr> 
  <tr> 
   <td></td> 
   <td> reviewStreamTitle </td> 
   <td> <i>Blank by default. Title of the summary section of the review.</i> </td> 
  </tr> 
  <tr> 
   <td colspan="2"> <i>Misc</i> </td> 
   <td></td> 
  </tr> 
  <tr> 
   <td></td> 
   <td> averageRating </td> 
   <td> <a href="https://d.pr/i/QscA" format="html" scope="external"> Average User Rating </a> </td> 
  </tr> 
  <tr> 
   <td></td> 
   <td> breakdownHeader </td> 
   <td> <a href="https://d.pr/i/QscA" format="html" scope="external"> Rating Breakdown </a> </td> 
  </tr> 
  <tr> 
   <td></td> 
   <td> helpful </td> 
   <td> %s of %s found helpful </td> 
  </tr> 
  <tr> 
   <td></td> 
   <td> helpfulPlural </td> 
   <td> %s of %s found helpful </td> 
  </tr> 
  <tr> 
   <td></td> 
   <td> outOf </td> 
   <td> / </td> 
  </tr> 
  <tr> 
   <td></td> 
   <td> ratingType </td> 
   <td> star </td> 
  </tr> 
 </tbody> 
</table>

## Stream Info {#section_wmv_yj4_xz}

Strings available for content stream information and display.

|  Element  | Key  | Default Text  |
|---|---|---|
|  *Sorting* | | |
|  | sortBy  | *Blank by default.* |
|  | sortHighestRated  | [Highest rating](https://d.pr/i/huTd)  |
|  | sortLowestRated  | [Lowest rating](https://d.pr/i/huTd)  |
|  | sortMostHelpful  | [Most helpful](https://d.pr/i/huTd)  |
|  *Stream misc.* | | |
|  | showMore  | Show More  |
|  *Stream high velocity* | | |
|  | newComment  | New Review  |
|  | newComments  | New Reviews  |
|  *Listener counts* | | |
|  | listenerCount  | person listening  |
|  | listenerCountPlural  | people listening  |
|  *Comment counts* | | |
|  | commentCountLabel  | LiveReviews<strong>|</strong>%s  |
|  | commentCountLabelPlural  | LiveReviews<strong>|</strong>%s  |
|  *Comment notifier counts* | | |
|  | commentNotifier  | New Review  |
|  | commentNotifierPlural  | New Reviews  |

## Author / Content Info {#section_osx_xj4_xz}

Stings available for author and individual content information.

|  Element  | Key  | Default Text  |
|---|---|---|
|  *Thread Breakout* | | |
|  | reviewsContentNotFoundMsg  | [This review is no longer visible](https://d.pr/i/svXs)  |
|  | backToComments  | Back to Reviews  |

## User Actions {#section_tlx_wj4_xz}

Strings available for user actions: flagging, sharing, and marking existing content as helpful.

|  Element  | Key  | Default Text  |
|---|---|---|
|  *Comment footer* | | |
|  | wasReviewHelpful  | [Helpful?](https://d.pr/i/Q0mA)  |
|  | wasReviewHelpfulMobile  | Helpful?  |
|  | ownWasReviewHelpful  | [Found helpful.](https://d.pr/i/Q0mA)  |
|  | reviewWasHelpful  | [Yes](https://d.pr/i/Q0mA)  |
|  | helpfulDivider  | [|](https://d.pr/i/Q0mA)  |
|  | reviewWasNotHelpful  | [No](https://d.pr/i/Q0mA)  |
|  *Vote modal* | | |
|  | voteTitle  | Was this review helpful?  |
|  | voteDownvote  | No  |
|  | voteReplyTitle  | Was this reply helpful?  |
|  | voteTitle  | Was this comment helpful?  |
|  | voteUpvote  | Yes  |
|  *Flag modal* | | |
|  | flagTitle  | Flag %s’s review  |
|  | flagSuccessMsg  | Review has been flagged.  |
|  *Flag Mobile* | | |
|  | flagConfirmationMessage  | Flag %s’s review as %s?  |
|  *Mention modal* | | |
|  | mentionDefaultText  | I mentioned you in a Livefyre review!  |
|  *Share modal* | | |
|  | shareTitle  | Share Review  |

## Post Functions {#section_yl1_wj4_xz}

Strings available for users posting reviews.

|  Element  | Key  | Default Text  |
|---|---|---|
|  *Editor* | | |
|  | bodyPlaceholder  | Write review…  |
|  | postEditButton  | Edit  |
|  | postEditCancelButton  | Cancel  |
|  | postAsButton  | Post review as…  |
|  | postButton  | Post review  |
|  | postReplyAsButton  | Post as…  |
|  | postReplyButton  | Post  |
|  | shareButton  | Share  |
|  | titlePlaceholder  | Title…  |

## Errors {#section_jbc_vj4_xz}

Strings available for general error messages.

|  Element  | Key  | Default Text  |
|---|---|---|
|  Errors  | | |
|  | errorAlreadyPosted  | You can only post one review.  |
|  | errorAuthError  | You’re not authorized to post a review on this conversation  |
|  | errorCommentsNotAllowed  | Reviews cannot be posted at this time  |
|  | errorDislikeOwnComment  | You cannot dislike your own review  |
|  | errorDuplicate  | As much as you liked your review, you’re not allowed to post it twice.  |
|  | errorEditDuplicate  | You must change the body of the review when you edit it.  |
|  | errorEditNotAllowed  | You’re not allowed to edit reviews on this conversation.  |
|  | errorEditTimeExceeded  | Sorry, your review editing period has expired.  |
|  | errorEmpty  | It seems you’re attempting to post an empty review.  |
|  | errorEmptyTitle  | It seems you’re attempting to post an empty title  |
|  | errorFieldRating  | star rating  |
|  | errorFieldReview  | review  |
|  | errorFieldTitle  | title  |
|  | errorMaxChars  | Sorry, your review is too long. Please edit and try again.  |
|  | errorMissingFields  | Please enter a  |
|  | errorRatingEmpty  | You cannot submit an empty rating  |
|  | errorRatingNotSet  | All ratings must be set  |
|  | errorRatingNotValid  | The rating must be an object  |
|  | errorShowMore  | There was an error loading more reviews.  |
|  | errorTitleMaxChars  | Sorry, your title is too long. Please edit and try again.  |
|  | errorVoteOwnComment  | You cannot vote on your own review  |

## Sidenotes Text Strings {#c_sidenotes_text_strings}

Customizing the text strings for Livefyre Sidenotes

<!-- 

c_sidenotes_text_strings.dita

 -->

This page lists and describes all strings available for customization in Sidenotes apps. For information on strings available for the core Livefyre apps, please see String Customizations.

* Implementation
* Auth
* Stream Info
* Author / Content Info
* User Actions
* Post Functions
* Moderator Interface
* Errors

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
|  *Auth menu strings* | | |
|  | menuAuthSignInBtn  | Sign in  |
|  | menuAuthSignedInMsg  | You must be signed in to {action}  |
|  | menuUserEditProfile  | Edit Profile  |
|  | menuUserAdmin  | Admin Console  |
|  | menuUserLogout  | Sign Out  |
|  | menuUserBackBtn  | All  |

## Stream Info {#section_wpy_gl4_xz}

Strings available for content stream information and display.

|  Element  | Key  | Default Text  |
|---|---|---|
|  *Info menu options* | | |
|  | menuInfoCopyright  | &copy; Livefyre, Inc. 2014  |
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
|  | datetimeMonths  | *An array. Default = *[ ‘January’, ‘February’, ‘March’, ‘April’, ‘May’, ‘June’, ‘July’, ‘August’, ‘September’, ‘October’, ‘November’, ‘December’ ]  |
|  | questionExplanation  | You can now read and write comments directly on sentences, paragraphs, images and quotes.<br><br><span class=”lf-highlight-text”>Highlight text</span> and click the <span class=”fycon-write”></span> icon or click the <span class=”fycon-action-view”></span> icon at the end of each paragraph.  |
|  | questionMockText  | What is “familiarly known” is not properly known, just for the reason that it is “familiar”.  |
|  | questionTitle  | What is a Sidenote?  |

## User Actions {#section_qxd_fl4_xz}

Strings available for user actions: flagging, sharing, and liking existing content.

|  Element  | Key  | Default Text  |
|---|---|---|
|  *Reply menu options* | | |
|  | menuRepliesViewTitle  | Details  |
|  | menuRepliesViewReply  | Reply to Conversation  |
|  *Share menu options* | | |
|  | menuShareOptionFacebook  | Facebook  |
|  | menuShareOptionTwitter  | Twitter  |
|  | menuShareTitle  | Share  |
|  *Flag menu options* | | |
|  | menuFlagOptionDisagree  | Disagree  |
|  | menuFlagOptionOffensive  | Offensive  |
|  | menuFlagOptionOffTopic  | Off Topic  |
|  | menuFlagOptionSpam  | Spam  |
|  | menuFlagTitle  | Flag as…  |
|  | facebookShareCaption  | Sidenotes on “{title}”  |
|  *Mobile user options* | | |
|  | sliderCommentTally  | of  |
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
|  *Delete menu options* | | |
|  | menuConfirmAccept  | Yes, {action}  |
|  | menuConfirmCancel  | Cancel  |
|  | menuConfirmTitle  | Are you sure?  |
|  *Etc menu options* | | |
|  | menuEtcOptionApprove  | Approve  |
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
|  *Confirmation messages from the More menu* | | |
|  | notificationApproved  | Approved  |
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

