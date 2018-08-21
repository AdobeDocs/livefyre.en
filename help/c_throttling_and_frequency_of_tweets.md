---
description: Not every tweet that matches a rule appears in a stream.
seo-description: Not every tweet that matches a rule appears in a stream.
seo-title: Throttling and Frequency of Tweets
solution: Experience Manager
title: Throttling and Frequency of Tweets
uuid: 0e3eba10-652c-44d4-a61b-c29934e0a16d
index: y
internal: n
snippet: y
translate: y
---

# Throttling and Frequency of Tweets

Twitter rule throttling and Twitter feed interruptions can limit the number of Tweets visible in the stream.

>[!NOTE]
>
>To guarantee that specific Tweets are included in your stream, use the Upload Asset option from the All Assets page.


* Twitter Rules throttle content, pulling 1 Tweet per rule every 5 seconds. This allows content appearing in Livefyre Apps to be more balanced, and not become overwhelmed with Tweets. Limiting incoming Tweets in this manner also helps to prevent the stream from becoming flooded or unreadable during high traffic periods.

  >[!NOTE]
  >
  >To ensure that your high-value authors’ content appears in your Apps, even in high-velocity streams, Rules for specific authors are never throttled.

* Twitter feed interruptions may occur for several reasons. In some cases, Twitter does not push out Tweets, therefore Livefyre does not receive notification of the new content, and it cannot be displayed. Service interruptions of Twitter’s APIs, or traffic on high volume hashtags/keywords, may also result in missed Tweets.