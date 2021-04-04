---
description: You can create Stream rules that pull content from Instagram.
seo-description: You can create Stream rules that pull content from Instagram.
seo-title: Instagram Rules
title: Instagram Rules
uuid: 98108ddb-5710-4331-891b-7e1bbb106059
exl-id: ac00a12c-94b1-4464-ad3f-991382759d71
---
# Instagram Rules{#instagram-rules}

You can create Stream rules that pull content from Instagram.

>[!NOTE]
>
>Before you create an Instagram stream, you must add at least one Instagram business account to the **[!UICONTROL Social Accounts]** section in **[!UICONTROL Network Settings]**. For more information on how to configure an Instagram account, see [About Instagram Accounts](../c-users-creating-accounts-with-studio-access/t-configure-social-accout-instagram/c-about-instagram-accounts.md#c_about_instagram_accounts).

Create Instagram Rules based on @mentions or hashtag.

>[!NOTE]
>
>All Instagram rules require at least one hashtag. Adding keywords and a username for your rule will return content which includes both entries.

To create Instagram rules to pull content from Instagram feeds into your App or Folder, filter by:

* **[!UICONTROL Words]**

    * Enter **[!UICONTROL hashtags]** to be included in, or excluded from your Instagram stream. Specifying values for both the **[!UICONTROL Contains]** and **[!UICONTROL Does not contain]** fields will return images which contain the first, and do not contain the second.
    
    * For example, entering **[!UICONTROL Contains]** keywords Giants, Posey, and **[!UICONTROL Does not contain]** keyword Dodger, will return all posts which include the word Giants or Posey, and do not include the word Dodger.    
    
      >[!NOTE]
      >
      >Instagram Rules will return posts which include the listed hashtag in the author’s comments, which may not appear in the stream.

* **[!UICONTROL Mentions]**

    * Enter **[!UICONTROL @mentions]** to pull into the stream, or exclude from the stream.

* **[!UICONTROL Authors]**

  >[!NOTE]
  >
  >You must have an Instagram business account set up in Livefyre to use the Author search in an Instagram Stream rule. For more information on setting up Instagram business accounts in Livefyre, see [About Instagram Accounts](../c-users-creating-accounts-with-studio-access/t-configure-social-accout-instagram/c-about-instagram-accounts.md#c_about_instagram_accounts).

    * Enter **[!UICONTROL @usernames]** to pull into the stream. The account associated with the **@username** must be an Instagram business account.
    
    * Enter the **@usernames** to exclude from the stream.

* **[!UICONTROL Additional Filters]**

    * Select whether you would like to include **[!UICONTROL All Content]**, **[!UICONTROL Videos Only]**, or **[!UICONTROL Photos Only]** in your stream.

For additional Stream rule options for all Stream rules, see [Stream Rule Options for All Stream Rules](../c-streams/c-stream-rule-options-for-all-stream-rules.md#c_stream_rule_options_for_all_stream_rules).
