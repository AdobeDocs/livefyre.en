---
description: These options apply for any stream rules from all social networks or posting methods.
title: Stream Rule Options for All Stream Rules
exl-id: eff1a3cb-395f-4eb1-be93-f0f09bba95e2
---
# Stream Rule Options for All Stream Rules{#stream-rule-options-for-all-stream-rules}

These options apply for any stream rules from all social networks or posting methods.

Search features for text and keyword fields:

* When you enter keywords, Livefyre automatically uses the Boolean operator **OR** when for individual words. For example, to search for posts with either the word *cake* or *recipe*, enter *cake*, then enter *recipe* in the **[!UICONTROL keyword]** field. 

* You can search for exact phrases by surrounding the exact phrase text in quotes. For example, to search for the exact phrase *cake recipe*, enter *"cake recipe"* in the **[!UICONTROL keyword]** field. 

* You can combine the Boolean and exact phrase searches in one stream rule. For example, you can search for *cake*, *recipe*, and *"cake recipe"* by entering each phrase one at a time.

**[!UICONTROL Additional Filters]**:

* **[!UICONTROL Media]**. Select one of the following:

  * **[!UICONTROL All Content.]** Allow any content. 
  * **[!UICONTROL Media Required.]** Allow only content with images and videos. (For Instagram and Facebook content, you can specify **[!UICONTROL Photos]** or **[!UICONTROL Videos]** only).

* **[!UICONTROL Language]**. Choose the language to search in. English is the default language. 
* **[!UICONTROL Smart Tags]**. Choose the tags to use to identify content. Livefyre uses computer vision technology to identify photos and videos with specific smart tags to make this search more precise. Use the **[!UICONTROL ANY]** modifier to filter content into the stream using any tag or the **[!UICONTROL ALL]** modifier to filter content into the stream that uses all tags. Use the **[!UICONTROL Image contains none of these smart tags]** field to enter tags for photos containing content you do not want in the stream. This option does not work for text content. 

* **[!UICONTROL Products]**. Add product tags to match the stream rule with products from your product catalog. 
* **[!UICONTROL Premoderate]**. Select one of the following:

  * **[!UICONTROL On]**. Premoderate all incoming rule content. You can view premoderated content from the Streams section of ModQ. **[!UICONTROL On]** overrides the settings in App Settings. 
  * **[!UICONTROL Off]**. Do not premoderate any incoming rule content. **[!UICONTROL Off]** overrides the settings in App Settings. 
  * **[!UICONTROL Inherited (Off)]**. Use the premoderate settings from the site (under **[!UICONTROL Site Settings]**).

* **[!UICONTROL SAFE Rules]**. Select one of the following:
  * **[!UICONTROL Apply SAFE Rules]**. Apply all SAFE Rules to this stream. 
  * **[!UICONTROL Apply SAFE Rules for:]** Select one or more of the options to apply SAFE Rules for this stream rule. 
  * **[!UICONTROL Disable SAFE Rules]**. Do not apply any SAFE Rules to this stream.

For Stream rule options specific to a social network or content type, see the following documentation for the respective social network or content type:

* [Facebook Pages](../c-streams/c-facebook-page-rules.md#c_facebook_page_rules) 
* [Email](../c-streams/c-email-rules.md#c_email_rules) 
* [Instagram](../c-streams/c-instagram-rules.md#c_instagram_rules) 
* [Tumblr](../c-streams/c-tumblr-rules.md#c_tumblr_rules) 
* [Twitter](../c-streams/c-twitter-rules.md#c_twitter_rules) 
* [YouTube](../c-streams/c-youtube-rules/c-youtube-rules.md#c_youtube_rules) 
* [RSS](../c-streams/c-rss-rules-streams.md#c_rss_rules_streams)
