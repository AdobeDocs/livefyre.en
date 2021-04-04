---
description: You can create Stream rules that pull content from RSS feeds.
seo-description: You can create Stream rules that pull content from RSS feeds.
seo-title: RSS Rules
solution: Experience Manager
title: RSS Rules
uuid: 3c9e2069-bb85-41dc-8b35-6237642a538a
exl-id: bfb3bbad-ab26-451e-b540-d6c41f54dc31
---
# RSS Rules{#rss-rules}

You can create Stream rules that pull content from RSS feeds.

RSS streams update every 5 minutes, looking for content that does not already exist in Livefyre from the first 50 items in the feed. Livefyre ignores everything past the first 50 items in the feed.

To create RSS Rules to pull content from RSS feeds into your App or Folder, you can filter by:

* **[!UICONTROL URL]** of the RSS Feed.
* **[!UICONTROL Include recent items.]** If this is set to:

    * **[!UICONTROL Enabled]**, Livefyre adds the first 50 content items in your feed to the stream, regardless of the publication date.
    * **[!UICONTROL Disabled]**, Livefyre adds the first 50 content items in your feed to the stream with a publication date that is the same as the stream rule creation date or later.

* **[!UICONTROL Extract post information from item link (when disabled, post information is extracted from XML).]** Pull information from the item link or from the XML.

**RSS Rules**

Livefyre parses RSS feeds based on the following RSS specs:

* [RSS 2.0](https://en.wikipedia.org/wiki/RSS)
* [Media RSS](https://en.wikipedia.org/wiki/Media_RSS)
* [Atom feed](https://validator.w3.org/feed/docs/atom.html)

Livefyre does not read feeds that do not adhere to these specs, and their content will not be pulled into your stream. Use the WC3 Feed Validation Service to check the syntax of your RSS feed, and ensure that it is valid.

For additional Stream rule options for all Stream rules, see [Stream Rule Options for All Stream Rules](../c-streams/c-stream-rule-options-for-all-stream-rules.md#c_stream_rule_options_for_all_stream_rules).
