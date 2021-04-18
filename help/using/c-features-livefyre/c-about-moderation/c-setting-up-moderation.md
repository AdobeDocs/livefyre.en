---
description: Use the Moderation tab to set premoderation rules for incoming content, including profanity lists, flag rules, and banned IP addresses.
title: Setting Up Moderation
exl-id: 09fc44c4-7ee1-47fd-ae68-885532a6f03f
---
# Setting Up Moderation{#setting-up-moderation}

Use the Moderation tab to set premoderation rules for incoming content, including profanity lists, flag rules, and banned IP addresses.

## How Moderation Works {#section_kyf_gvc_t1b}

You can moderate content in the following ways:

* Automatically premoderate content to filter out undesired content based on rules you set up before you publish the content.
* Manually delete or approve content that was flagged using the automatic premoderation using the ModQ or App Content in the Library.
* Identify site visitors that repeatedly post offensive content to keep them from posting by banning specific Livefyre users, social users, or IP addresses. 
* Identify people and content that can always display by allow-listing users or turning off filters for specific streams, sites, or networks.

You can automatically premoderate content in the following ways:

* Set up rules to automatically flag certain types of content:

  * Set up flag rules for content that is flagged by site visitors flag using **[!UICONTROL Settings > Moderation > Rules]**
  * Set up SAFE rules using **[!UICONTROL Settings > Moderation > Rules]**
  * Ban specific Twitter users using **[!UICONTROL Settings > Streams]** 
  * Ban IP addresses using **[!UICONTROL Settings > Bans]**
  * Ban IP regions by country code by request. Banned content will be marked as SPAM.

* Create a list of words that you consider profanity in the Profanity List under **[!UICONTROL Settings > Moderation > Rules]** for your Network or Site.
* Allow-list users (always allow content from these users to display) by using or turning off filters for specific streams, sites, or networks.

After you have set up your profanity lists, SAFE filters, and rules, you can choose whether to premoderate content and apply the SAFE filters in streams. For more information, see [Stream Rule Options for All Stream Rules](/help/using/c-streams/c-stream-rule-options-for-all-stream-rules.md#c_stream_rule_options_for_all_stream_rules).

Livefyre marks content as **[!UICONTROL Approved]**, **[!UICONTROL Pending]**, **[!UICONTROL Junk]**, etc. depending on where the content comes from, where it will be published, and what rules you have set up in your system. The following table describes the actions Livefyre takes, depending on these factors, in detail.

## How Moderation Works

|Content Comes From:|Sending Content To:|Approval Status|
|--- |--- |--- |
|Library|App|Content Approved|
|Social Search|App|Content Approved|
|Stream Rule|App|Is content marked as Junk by SAFE filter? <br><ul><li>No -  Stream-to-App Moderation Workflow</li><li>Yes - Content Trashed</li></ul>|
|Library|Folder|No status (in folder, not published, not trashed)|
|Social Search|Folder|No status (in folder, not published, not trashed)|
|Stream Rule|Folder|Is content marked as Junk by SAFE filter? <br><ul><li>No - No status (in folder, not published, not trashed)</li><li>Yes - Content Trashed</li></ul>|
|App Post|App|Is content marked as Junk by SAFE filter? <br><ul><li>No -  Post-to-App Moderation Workflow</li><li>Yes - Content Trashed</li></ul>|

## Stream-to-App Moderation Workflow {#section_z5z_w4d_t1b}

![](assets/stream_to_app_workflow.png)

Before the content from a Stream is published to an App, Livefyre performs the following checks to determine what to do with the content:

1. If SAFE flags the content as junk or drop, Livefyre trashes the content. 
1. If SAFE does not flag the content as junk, Livefyre checks to see if premoderation is on. 
1. If premoderation is on, Livefyre marks the content as pending. 
1. If you set up ModQ rules, then Livefyre sends the content to ModQ.
1. If premoderation is not on, Livefyre checks to see if SAFE flagged the content. 
1. If SAFE flagged the content, Livefyre approves the content and publishes the content to the App.
1. If SAFE flags the content and you did not set up SAFE rules, then Livefyre approves the content and publishes the content to the App.
1. If SAFE flags the content and you set up SAFE rules, Livefyre checks if you set up SAFE rules for the Stream. 
1. If you set up SAFE rules for the stream, Livefyre approves the content and publishes the content to the App. If you did not set up SAFE rules for the stream, Livefyre uses the moderation SAFE rules to determine how to handle the content (send to ModQ, trash, etc.).

## Post-to-App Moderation Workflow {#section_fwn_w4d_t1b}

![](assets/post_to_app_workflow.png)

Before the content from an App post is published to an App, Livefyre performs the following checks to determine what to do with the content:

1. If the SAFE filter flags the content as drop, Livefyre drops the content. 
1. If SAFE does not flag the content as drop, Livefyre checks to see if premoderation is on. If premoderation is on, Livefyre marks the content as pending. If you set up ModQ rules, then Livefyre sends the content to ModQ as pending. If not, the content remains in a pending status in App Content in the Library.
1. If premoderation is not on, Livefyre checks to see if SAFE flagged the content. If not, Livefyre approves the content and publishes the content to the App.
1. If SAFE flags the content and you set up SAFE rules, Livefyre uses the SAFE rule to determine how to handle the content (send to ModQ, trash, etc.). If SAFE flags the content and you did not set up SAFE rules, then Livefyre approves the content and publishes the content to the App.

## Bulk Filters {#section_lyk_ktx_vy}

The Bulk Filter looks for repetitive content posted across all Livefyre networks within a short timeframe. If detected, this content is flagged as Bulk, and then trashed by default. While bulk content may be user-generated (such as “Touchdown!” posted repeatedly in a Chat during a popular football game), most originates with spam campaigns. This filter is language-independent, and works with any language. To customize the bulk filter, you must contact Livefyre support.

## Rules {#section_gqz_ksk_f1b}

Use the Rules section to create pre-moderation rules, based on SAFE and user applied flags. This panel offers two types of rules:

* **[!UICONTROL Flag Rules:]** specify an action that should be taken on a comment flagged by users a defined number of times.
* **[!UICONTROL SAFE Rules:]**combine SAFE flags with actions to take on the flagged content.

To create Flag Rules, select the flag (Offensive, Off Topic, Disagree, or Spam), enter the number of times it must be applied to a piece of content, and select the action to take. You can set one Flag Rule for each flag option (Offensive, Off Topic, Disagree, or Spam).

You can create rules at the Network, Site, and Stream levels. Site level rules inherit network rules, unless you configure Site rules differently. Stream rules inherit Site rules unless you configure them differently.

Available actions:

* **[!UICONTROL Trash it:]**sends the flagged comment to the trash.
* **[!UICONTROL Bozo it:]** hides the flagged comment from all users, except its writer, to whom it remains visible.
* **[!UICONTROL Pending:]** sets the content as pending. If you set Premoderation to ON under **[!UICONTROL Settings > ModQ]**, then it will be in the ModQ. Otherwise it will be in App Content only.

>[!NOTE]
>
>Livefyre recommends that you create rules to Bozo comments that are flagged as Spam or Offensive by five users.

## Moderation Recommendations {#section_ec3_vr3_2cb}

You can use moderation recommendations to help you determine how to moderate content posted by site visitors in Livefyre Apps. The Moderation Recommendation Indicator recommends when a piece of content is likely to be trashed, based on what actions you took previously on similar content. To use Moderation Recommendations:

1. Turn on the Moderation Recommendations functionality by contacting your Adobe Livefyre support professional.
1. Set up moderation recommendations in Network Settings.

   Set up moderation recommendations using the **[!UICONTROL Livefyre Recommends Trash]** setting under **[!UICONTROL Network Settings]**. 

   ![](assets/image_mod_reco_trash.png)

1. Set up a SAFE rule to tell Livefyre what to do with content that the moderation recommendation identifies as content that is likely to be trashed. For more information on how to set up a SAFE rule for the **[!UICONTROL Livefyre Recommends Trash]** option, see [Moderation](/help/using/c-features-livefyre/c-about-moderation/c-moderation.md#c_moderation).

   ![](assets/modreco4.png)

1. Use the **[!UICONTROL Moderation Recommendation Indicator]** in the ModQ or in App Content to filter content that the moderation recommendation identifies as likely to be trashed.

   In ModQ, the indicator looks like this:  ![](assets/mod_reco1.png)

   For more information on how to use Moderation Recommendations to moderate content in ModQ, see [ModQ](/help/using/c-features-livefyre/c-about-moderation/c-modq.md#c_modq).

   In App Content, moderation recommendations look like this:  ![](assets/modreco3.png)

   For more information on how to use Moderation Recommendations in App Content, see [Moderate Content Using App Content](/help/using/c-features-livefyre/c-about-moderation/c-moderate-content-using-app-content.md#c_moderate_content_using_app_content).
