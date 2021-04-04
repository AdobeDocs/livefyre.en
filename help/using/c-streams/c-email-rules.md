---
description: You can create Stream rules that pull content from Email.
seo-description: You can create Stream rules that pull content from Email.
seo-title: Email Rules
solution: Experience Manager
title: Email Rules
uuid: 3cd27d28-b7c0-4cbc-bae3-e2ef7beacba9
exl-id: 19c586f7-b934-40b5-bc9a-8a8a734e5467
---
# Email Rules{#email-rules}

You can create Stream rules that pull content from Email.

Creating Email based Streams allows you to post content directly to an App or Folder by email.

Use this feature to allow your contributors to post directly to your Apps or Asset Library from their computer or mobile device.

Once the rule is created, any email containing an image or video file sent to the listed email address will be posted directly to your App or Asset Library, as specified. Emails sent with multiple attachments will post all files to the appropriate location. Emails sent to the listed address containing only text will do nothing.

Once sent, the email’s fields will be used to populate the following items for the piece of content:

* **[!UICONTROL From:]** Used as the content’s author, if the user account exists. If no account exists for the sender, the author is listed as anonymous.
* **[!UICONTROL Subject:]** Used for the content’s title.
* **[!UICONTROL Body:]** Used to populate content details within Studio.
* **[!UICONTROL Attachments:]** Media files must be attached, or the email will be ignored. Supported file types include 3GP, ASF, AVI, DV, GIF, JPG, MOV, MP4, MPEG, MPG, PNG, QT, and WMV. The total of all attachments must be below 25MB file size.

For additional Stream rule options for all Stream rules, see [Stream Rule Options for All Stream Rules](../c-streams/c-stream-rule-options-for-all-stream-rules.md#c_stream_rule_options_for_all_stream_rules).
