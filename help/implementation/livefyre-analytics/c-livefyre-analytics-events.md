---
title: Livefyre Analytics Events
description: Livefyre Analytics Events
exl-id: ec32414c-0580-44dc-ae5b-6df0b42c0ec3
---
# Livefyre Analytics Events

## Event Object Definition {#section_dh1_yhn_pdb}

The following code defines the fields in the event object that get received by the analytics handler on a page.

```
{
  evars: {
    appId : string : URN ID of the app
    appType : string : Type of the app
    contentType : string : Type of the content that this event pertains to
    contextId : string : URN ID of the contextual item that this event pertains to
    environment : string : Environment that this app is using
    networkId : string : Network that this app is using
    publishedDate : number : Epoch time when the app was published
    userLoggedIn : boolean : If a user is logged in
  },
  generator: {
    env : string: Environment that this app is using
    id : string: URN ID of the app
    name : string: Name of the app
    networkId : string: Network that this app is using
    source : string: URN of the collection
    version : string: Semver version of the app
  },
  startTime : number: Epoch time when event was created
  type : string: Event type (Table 1)
}

```

## Livefyre Analytics Events and eVars {#section_u3k_tft_mcb}

The following Livefyre events to map to custom events to use in reports using the Report Suite Manager. For more information about Report Suites in Adobe Analytics, see [Report Suite Manager](https://docs.adobe.com/content/help/en/analytics/admin/manage-report-suites/report-suites-admin.html). For more on how to use Livefyre events with Report Suite Manager, see [](../livefyre-analytics/c-use-livefyre-with-adobe-analytics.md#section_iks_kgd_4cb).

## Livefyre Analytics Events

|  Event | Description |
|---|---|
|  Init | When a page that includes at least one Livefyre app is loaded |
|  Load | Any time an app was loaded on a page regardless of user view |
|  View | When an app entered the viewport for the first time. |
|  Post | Any time a user posts a comment or a piece of content including ex: top level post, replies, reviews, media wall uploads  |
|  Posted | When a post was successsful. |
|  Twitter_Reply | Any time a user replied on Twitter |
|  Twitter_Like | Where content was shared to: Retweet |
|  Livefyre_Like | Any time the livefyre like feature is used in an app |
|  Livefyre_Unlike | Any time a user unlikes a livefyre like  |
|  ShareOnPost | Anytime a user posts content and uses the share on post feature |
|  ShareButtonClick | Any time a user clicks on the share button on a comment |
|  ShareTwitter | When Share to Twitter is clicked |
|  ShareFacebook | When Share to Facebook is clicked |
|  ShareURL | When Share to URL text area is selected/copied. |
|  ExpandReplies  | When a user clicks on the + or Expand link to view all replies on a top level post |
|  CollapseReplies  | When a user clicks on the - or Collapse link to view all replies on a top level post |
|  FlagClick | Any time a user opens the Flag Modal |
|  FlagSpam | When a user flags content as spam |
|  FlagDisagree | When a user flags content as disagree |
|  FlagOffensive | When a user flags content as offensive |
|  FlagOffTopic | When a user flags content as off topic |
|  FlagCancel  | Any time a user clicks X or "cancel" when submitting a flag |
|  FollowCollection | Any time a conversation is followed ("I'm interested" in Reviews)  |
|  UnfollowCollection | When a conversation is unfollowed |
|  RequestMore | Any time a user loaded more content in an app (needs to be for high velocity too)  |
|  ModalView | Any time a user clicks to view content in a modal |
|  TwitterRetweetClick | Where content was shared to: Retweet |
|  PostButtonClick | When a user clicks on the post ("Whats on your mind?") button |
|  Login | Any time a user logged in |
|  Logout | Any time a user logged out |

The following is a list of conversion variables (eVars) that Livefyre provides.

## Conversion Variables - eVars

|Event|Description|
|--- |--- |
|Network ID|Network ID/Name in Livefyre|
|App ID|The URN of the app|
|Context ID|Content ID in Livefyre|
|App Type|Livefyre App Type. Options: <br><ul><li>Live Blog  </li><li> Feature Card</li><li>Carousel</li><li>Chat </li><li>Comments</li><li>Filmstrip</li><li>Map</li><li>Mosaic</li><li>Media Wall</li><li>Trending</li><li>Upload Button</li></ul>|
|Content Type|Instagram, Twitter, Facebook, LiveFyre, YouTube, etc|

## More Info {#section_b3d_4yl_pdb}

For more information on the topics discussed on this page, see:

* [Report Suite Manager](https://docs.adobe.com/content/help/en/analytics/admin/manage-report-suites/report-suites-admin.html)[DTM](https://docs.adobe.com/content/help/en/livefyre/using/apps/filmstrip/c-filmstrip-app.html)

* [Rules](https://docs.adobe.com/content/help/en/dtm/using/resources/rules/create-rules.html)
* [Livefyre.js](/help/implementation/c-livefyre.js.md)
