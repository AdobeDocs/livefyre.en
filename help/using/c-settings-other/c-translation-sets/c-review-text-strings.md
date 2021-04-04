---
description: Customizing the text strings for Livefyre Reviews.
seo-description: Customizing the text strings for Livefyre Reviews.
seo-title: Review Text Strings
solution: Experience Manager
title: Review Text Strings
uuid: 86251e49-bc73-4eec-9f9b-b4b0a5b42099
exl-id: 82ced091-d573-4514-9b91-3451a94ed5d3
---
# Review Text Strings{#review-text-strings}

Customizing the text strings for Livefyre Reviews.

This page lists and describes the strings available for customization in Review apps. The strings listed here are in addition to and overrides for the default strings for Livefyre core apps, listed in String Customizations. Where duplicates are listed, the strings listed in these tables are the default for Reviews apps.

Implementation
Review / Rating Interface
Stream Info
Author / Content Info
User Actions
Post Functions
Errors

## Implementation {#section-vsy-1k4-xz}

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

|Element|Key|Default Text|
|--- |--- |--- |
|Buttons|editReviewBtn|Edit review|
||reviewBtn|[Write review](https://d.pr/i/QscA)|
||reviewsClosed|[Reviews Closed](https://d.pr/i/zr7M)|
||showReviewBtn|[Show review](https://d.pr/i/onxU)|
||follow|I’m interested|
||shareText|I just wrote a review. Check it out!|
|Rating tooltips|ratingValues|An array. Default = `[‘Poor’, ‘Poor’, ‘Fair’, ‘Fair’, ‘Average’, ‘Average’, ‘Good’, ‘Good’, ‘Excellent’, ‘Excellent’]`; <br>Note: Values in the array must be duplicated to assign both the left and the right half of each star the same name.|
|Rating subparts|ratingSubpartPlaceholders|An array. Default = `[]`|
||ratingSubpartTitles|An array. Default = `[]`|
||reviewStreamTitle|Blank by default. Title of the summary section of the review.|
|Misc|averageRating|[Average User Rating](https://d.pr/i/QscA)|
||breakdownHeader|[Rating Breakdown](https://d.pr/i/QscA)|
||helpful|%s of %s found helpful|
||helpfulPlural|%s of %s found helpful|
||outOf|/|
||ratingType|star|

## Stream Info {#section_wmv_yj4_xz}

Strings available for content stream information and display.

|  Element  | Key  | Default Text  |
|---|---|---|
| Sorting | sortBy  |Blank by default.|
|  | sortHighestRated  | [Highest rating](https://d.pr/i/huTd)  |
|  | sortLowestRated  | [Lowest rating](https://d.pr/i/huTd)  |
|  | sortMostHelpful  | [Most helpful](https://d.pr/i/huTd)  |
| Stream misc. | showMore  | Show More  |
| Stream high velocity | newComment  | New Review  |
|  | newComments  | New Reviews  |
| Listener counts| listenerCount  | person listening  |
|  | listenerCountPlural  | people listening  |
| Comment counts | commentCountLabel  | LiveReviews<strong>|</strong>%s  |
|  | commentCountLabelPlural  | LiveReviews<strong>|</strong>%s  |
| Comment notifier counts | commentNotifier  | New Review  |
|  | commentNotifierPlural  | New Reviews  |

## Author / Content Info {#section_osx_xj4_xz}

Stings available for author and individual content information.

|  Element  | Key  | Default Text  |
|---|---|---|
| Thread Breakout | reviewsContentNotFoundMsg  | [This review is no longer visible](https://d.pr/i/svXs)  |
|  | backToComments  | Back to Reviews  |

## User Actions {#section_tlx_wj4_xz}

Strings available for user actions: flagging, sharing, and marking existing content as helpful.

|  Element  | Key  | Default Text  |
|---|---|---|
| Comment footer | wasReviewHelpful  | [Helpful?](https://d.pr/i/Q0mA)  |
|  | wasReviewHelpfulMobile  | Helpful?  |
|  | ownWasReviewHelpful  | [Found helpful.](https://d.pr/i/Q0mA)  |
|  | reviewWasHelpful  | [Yes](https://d.pr/i/Q0mA)  |
|  | helpfulDivider  | [&vert;](https://d.pr/i/Q0mA)  |
|  | reviewWasNotHelpful  | [No](https://d.pr/i/Q0mA)  |
| Vote modal | voteTitle  | Was this review helpful?  |
|  | voteDownvote  | No  |
|  | voteReplyTitle  | Was this reply helpful?  |
|  | voteTitle  | Was this comment helpful?  |
|  | voteUpvote  | Yes  |
| Flag modal | flagTitle  | Flag %s’s review  |
|  | flagSuccessMsg  | Review has been flagged.  |
| Flag Mobile | flagConfirmationMessage  | Flag %s’s review as %s?  |
| Mention modal | mentionDefaultText  | I mentioned you in a Livefyre review!  |
| Share modal | shareTitle  | Share Review  |

## Post Functions {#section_yl1_wj4_xz}

Strings available for users posting reviews.

|  Element  | Key  | Default Text  |
|---|---|---|
| Editor | bodyPlaceholder  | Write review…  |
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
|  Errors  | errorAlreadyPosted  | You can only post one review.  |
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
