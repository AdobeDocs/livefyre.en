---
title: Using the Profanity Filter
description: Using the Profanity Filter
exl-id: 6ea7d913-f562-42a5-a6ea-241aa4e1089a
---
# Using the Profanity Filter{#using-the-profanity-filter}

All content posted into a Livefyre App is checked for profanity. If a word included in the profanity list is found in content or in a user’s display name, that content will be flagged “Profanity,” allowing you to filter it for Premoderation, Rules, ModQ, or general searches in App Content.

>[!NOTE]
>
>Studio Administrators’ and Managers’ content is not subject to the Profanity Rule check, and content posted by a Moderator will not be flagged.

Livefyre provides a default profanity list. You may choose to apply this list at the network level, provide your own list, or use an aggregate of the two. Individual sites within your network may inherit the network Profanity List, or use a list customized to be site-specific.

To provide your own custom profanity list as your network default, please send it to your Livefyre account manager.

## Enabling Profanity Filtering {#section_yqc_qsk_f1b}

Enable and configure the profanity filter at both the network and site level. Disable the profanity filter at the network level to automatically disable the profanity filter for all sites that inherit from the network.

>[!NOTE]
>
>All content passing through Livefyre is checked for profanity. If content is found which includes words contained on the default SAFE profanity list or in your custom Profanity list, it is flagged “Profanity.” To set Livefyre to automatically take action on these items, turn **[!UICONTROL Enable Profanity Checking]** to **[!UICONTROL ON]**.

## Enable the Profanity Filter for a Network {#section_twd_ssk_f1b}

1. Select **[!UICONTROL Network]** from the network pulldown menu.
1. Go to **[!UICONTROL Settings > Network Settings > Moderation]**.
1. Scroll down to the **[!UICONTROL Profanity List]**, and set **[!UICONTROL Enable Profanity Checking]** to **[!UICONTROL ON]**.

1. Use the **[!UICONTROL Update Network Profanity List]** field to add words to the list, or click a word to remove it from the list.

>[!NOTE]
>
>Editing the network level Profanity List will not affect any site-level Lists already in place. To ensure that changes from the network are made to the site, select **[!UICONTROL Restore Network List]** for the site after the changes have been made.

## Enable the Profanity Filter for a Site {#section_fld_wsk_f1b}

1. Select the site from the network pulldown menu.
1. Go to **[!UICONTROL Settings > Site Settings > Moderation]**.
1. Scroll down to the **[!UICONTROL Profanity List]** and set **[!UICONTROL Enable Profanity Checking]** to **[!UICONTROL ON]**.

1. Choose one of the following options:

    * To inherit the Profanity List from the network (this is not common), set **[!UICONTROL Use Site Profanity List]** to **[!UICONTROL OFF]**. 
    
    * To edit the Profanity List specifically for the site, set **[!UICONTROL Use Site Profanity List]** to **[!UICONTROL On]** to open the **[!UICONTROL Update Profanity List]** field, where you can edit the list:

        * To remove a word, click on the word.
        * To add a word, type the word into the **[!UICONTROL Add new word]** box and hit **[!UICONTROL Return]**.
        
        * To see if a word is included in the list, type the word into the **[!UICONTROL Test profanity filter]** box.

    * To reimport the network Profanity List and apply it to the site, click **[!UICONTROL Restore Network List]**.
    * To clear all content from the list and start from scratch, click **[!UICONTROL Clear List]**.

## Working with Content that Contains Profanity {#section_epy_dtk_f1b}

Use the Profanity List to help filter your content searches and to create Premoderation Rules for ModQ.

To search for content containing profanity, go to **[!UICONTROL Library > App Content]**, **[!UICONTROL Filter by Flags]** and check the **[!UICONTROL Profanity]** checkbox. All content that has been caught by the Profanity Filter for the site or network selected will be displayed. This list will include content pulled into the App using SocialSync and Streams.

To create Premoderation rules, from Studio select **[!UICONTROL Settings > Network Settings > Moderation]**. Once the profanity filter has been enabled, a new rule will appear, allowing you to Flag or Premoderate content containing profanity. By default, this rule automatically enables **[!UICONTROL Premoderate]** for profane content, which may be changed to either **[!UICONTROL Trash it]** or **[!UICONTROL Bozo it]**.

>[!NOTE]
>
>If a single piece of content is subject to multiple rule types (such as both SAFE and Flag rules), the more stringent will be applied. For example: If your Premoderation rule says to Premoderate a piece of content, but a SAFE Rule says to Trash it, it will be Trashed.

## View and Update the Profanity List for a Network {#section_qdb_btk_f1b}

1. Go to **[!UICONTROL Settings > Network Settings > Moderation]**.
1. Scroll down to the **[!UICONTROL Profanity List]** section.
1. Set **[!UICONTROL Enable Profanity Checking]** to **[!UICONTROL On]** to display the List enabled for your network (Livefyre default, or your uploaded custom list) and edit it. You can edit the list in the following ways:
    * To remove a word, click on the word.
    * To add a word, type the word into the **[!UICONTROL Add new word]** box and hit **[!UICONTROL Return]**.
    * To see if a word is included in the list, type the word into the **[!UICONTROL Test profanity filter]** box.

>[!NOTE]
>
>Only Studio Administrators and Moderators can edit Profanity Lists.
