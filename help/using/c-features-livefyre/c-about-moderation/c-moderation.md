---
description: The Livefyre Spam and Abuse Filtering Engine (SAFE), is a background process that analyzes all incoming content, and is enabled for all Livefyre customers.
seo-description: The Livefyre Spam and Abuse Filtering Engine (SAFE), is a background process that analyzes all incoming content, and is enabled for all Livefyre customers.
seo-title: SAFE Rules
title: SAFE Rules
uuid: 2f91d0d4-dffe-4651-88af-79bbb96c1b5c
exl-id: 13cd8df0-c4b7-436e-ba07-64ec67321d6b
---
# SAFE Rules{#safe-rules}

The Livefyre Spam and Abuse Filtering Engine (SAFE), is a background process that analyzes all incoming content, and is enabled for all Livefyre customers.



SAFE uses pattern rules as well as statistical models to detect spam, abuse, profanity, and bulk (repetitive) posts. You will see it referenced from time to time in other Livefyre products, notably the Content moderation tools and ModQ.

>[!NOTE]
>
>SAFE is English only, except for Bulk mailing classification. If you require support for other languages, please contact your Strategic Account Manager.

## Studio Components using SAFE {#section_k34_4tx_vy}

Flags applied by SAFE can be used with the following Studio components:

* Rules

  You can define SAFE rules to automatically flag content and define how flagged content should be handled in the **[!UICONTROL Network Settings]**.

  For example, a site may set a very low tolerance for Profanity and define SAFE Rules that set all content flagged as Profane to be Bozo’d. Other sites may define Rules which set Profane content to be pre-moderated before entering the stream.

* ModQ

  You can moderate content flagged by SAFE rules, and other premoderation rules (for example, SPAM, profanity, etc.), in the ModQ. 

* App Content in the Library

  Content flagged by SAFE is listed in the App Content in the **[!UICONTROL Library]** tab. You can filter content by flags to moderate content.

## SAFE Filter Options {#section_pg5_ttx_vy}

SAFE applies the following flags to filtered content and can be used to create rules and moderate content from within Livefyre Studio.

* **[!UICONTROL Profanity List]**: Profane content, as defined by a list of English keywords, based on common use.

  The Profanity Filter looks for profane language, based on a tested word list. If detected, the content is flagged Profane.

  >[!NOTE]
  >
  >Livefyre also provides a second Profanity List filter, which you can customize at both the Site and Network levels. Rules created with the Profanity List will take precedence over automated rules stemming from the SAFE Profanity filter. For more information, please see the Profanity List section in the Settings documentation.

* **[!UICONTROL Mild Profanity]**: Words and phrases generally not acceptable in polite conversations, but are usually acceptable in casual conversations. Generally, these words and phrases are allowed on network television. 
* **[!UICONTROL Strong Profanity]**: Very strong language, such as expletives and phrases not allowed on network television and used sparingly in R-rated movies and mature cable TV shows. Generally these words are not used in polite or casual conversation and are said in an impolite conversation with an intent to harm the listener.
* **[!UICONTROL SPAM]**: Unsolicited, usually commercial content. It uses a statistical model that relies on a variety of features (including comment content and URLs) to flag a piece of content as SPAM. You can adjust spam thresholds to customize SPAM tagging rates for your network or site, by request.
* **[!UICONTROL Mild Insult]**: Insulting content, as defined by a list of keywords and phrase patterns.
* **[!UICONTROL Strong Insult]**: Insulting content, as defined by a list of keywords and phrase patterns.
* **[!UICONTROL Hate Speech]**: An insult based on ethnicity or religion, especially when the target group affiliation is in a minority or protected.
* **[!UICONTROL ALL CAPS]**: Text presented in all capital letters (read as yelling).
* **[!UICONTROL Mild Threat]**: A threat or insult that usually includes some kind of mild profanity directed at another person. This option flags possible threats more often, but also has a higher false-positive rate than **[!UICONTROL Strong Threat]**. 

* **[!UICONTROL Strong Threat]**: A serious threat or insult that mentions actionable bodily harm to one or more people, often with strong profanity. This option flags possible threats less often, but also has a lower false-positive rate than **[!UICONTROL Mild Threat]**. 

* **[!UICONTROL Probable Nudity]**: An image that may have nudity in it. This option flags nudity less often, but also has a lower false-positive rate than **[!UICONTROL Possible Nudity]**.

* **[!UICONTROL Possible Nudity]**: An image that may have nudity in it. This option flags nudity more often, but also has a higher false-positive rate than **[!UICONTROL Probable Nudity]**.

* **[!UICONTROL PII]** (Personally-Identifiable Information): Information which can identify the user. This can include an email address, physical address, social security number (for US customers), credit card number, a password, or anything that can be used in fraud or to gain someone’s identity.
* **[!UICONTROL Livefyre Recommends Trash]**. Set the action that the system performs when the automated Moderation Recommendation identifies content for rejection.  ![](assets/mod_reco1.png)

  >[!NOTE]
  >
  >To turn on Moderation Recommendations, contact your Adobe Livefyre support professional.

## Handling Content not caught by SAFE {#section_pjy_5tx_vy}

There are several means available to effectively handle content not caught by this filter. Options below are listed in the recommended order of process.

1. As a moderator, remove the content from the stream.
1. Create a Flag Rule that says if a piece of content is flagged as Spam or Offensive by five users, set it to Bozo.
1. Ban the user that is posting unwanted content, so all their content will go directly into the Bozo state.
1. Add specific words that should always be filtered to your profanity list.

>[!NOTE]
>
>If a moderator posts content that is caught by our Spam Filter, it is still flagged as Spam, but is automatically Approved, and will not be set to Bozo.

If you notice trends or patterns of content not caught by SAFE, email your CSMs with the Comment IDs and text.



Apps that use this feature:

* [Carousel](/help/using/c-about-apps/c-carousel-app/c-carousel-app.md#c_carousel_app)
* [Chat](/help/using/c-about-apps/c-chat-app/c-chat-app.md#c_chat_app)
* [Comments](/help/using/c-about-apps/c-comments/c-comments.md)
* [Feature Card](/help/using/c-about-apps/c-feature-card-app/c-feature-card-app.md#c_feature_card_app)
* [Map](/help/using/c-about-apps/c-map-app/c-map-app.md#c_map_app)
* [Media Wall](/help/using/c-about-apps/c-media-wall-app/c-media-wall-app.md#c_media_wall_app)
* [Mosaic](/help/using/c-about-apps/c-mosaic-app/c-mosaic-app.md#c_mosaic_app)
* [Reviews](/help/using/c-about-apps/c-reviews-app/c-reviews-app.md#c_reviews_app)
* [Sidenotes](/help/using/c-about-apps/c-sidenotes-app/c-sidenotes-app.md#c_sidenotes_app)
* [Storify 2](/help/using/c-about-apps/c-storify2/c-storify2.md#c_storify2)
* [Upload Button](/help/using/c-about-apps/c-upload-button-app/c-upload-button-app.md#c_upload_button_app)
