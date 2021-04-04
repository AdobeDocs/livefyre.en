---
description: Use Bootstrap and Stream API with Livefyre Apps.
seo-description: Use Bootstrap and Stream API with Livefyre Apps.
seo-title: Use Bootstrap and Stream API with Livefyre Apps
solution: Experience Manager
title: Viewing Account Details
uuid: bace558f-ade8-49d6-abda-9ee754ce4ac0
exl-id: b8458954-3727-4c4d-93dd-d21a4328e069
---
# Use Bootstrap and Stream API with Livefyre Apps {#bootstrap-stream-api}

## Bootstrap API {#bootstrap-api}

### How can I retrieve content older than the newest 50 pieces? {#howcontentolder}

Bootstrap is all content in a Livefyre App. It is the cached data, typically 12-20 minutes old. It is delivered in chunks of 50 pieces and is paginated so you can retrieve content older than 50 pieces.

[API Reference](https://api.livefyre.com/docs/apis/by-category/collections#operation=urn:livefyre:apis:bootstrap:operations:bs3:v3.1:network:site:article:init:method=get)

[Example request](https://data.livefyre.com/bs3/v3.1/dharam.fyre.co/384931/NTU1NQ==/init)

The example request above loads the `init` page which contains Collection Settings and the only initial set of ~50 pieces of newest content. To poll older content, you must load subsequent bootstrap pages with `N` being the page number:

Request: `https://{networkName}.bootstrap.fyre.co/bs3/v3.1/{network}/{siteId}/{b64articleId}/N.json`

For example, a sample app has 120 pieces of content. Content "1" is the oldest piece of content and Content "70" is the newest piece of content.

* `Init` will load ~120-70 pieces of content in descending order: [https://data.livefyre.com/bs3/v3.1/dharam.fyre.co/384931/NTU1NQ==/init](https://data.livefyre.com/bs3/v3.1/dharam.fyre.co/384931/NTU1NQ==/init)

* `O.json` will load ~ 1-50 pieces of content in ascending order: [https://data.livefyre.com/bs3/v3.1//dharam.fyre.co/384931/NTU1NQ==/0.json](https://data.livefyre.com/bs3/v3.1//dharam.fyre.co/384931/NTU1NQ==/0.json)

* `1.json` will load ~ 51-100 pieces of content in ascending order: [https://data.livefyre.com/bs3/v3.1//dharam.fyre.co/384931/NTU1NQ==/1.json](https://data.livefyre.com/bs3/v3.1//dharam.fyre.co/384931/NTU1NQ==/1.json)

* `2.json` will load ~101-120 pieces of content in ascending order:[https://data.livefyre.com/bs3/v3.1//dharam.fyre.co/384931/NTU1NQ==/2.json](https://data.livefyre.com/bs3/v3.1//dharam.fyre.co/384931/NTU1NQ==/2.json)

[Click here to see the Bootstrap Poll Flowchart.](https://marketing-resource-help.s3.amazonaws.com/resources/help/en_US/livefyre/bootstrap-poll-flowchart.pdf)

## Stream API {#stream-api}

What is Stream API?
Stream is a long poll which by design is intended to stay open for approximately 30 seconds. Description on Long Polling technique can be found here: [https://stackoverflow.com/questions/11077857/what-are-long-polling-websockets-server-sent-events-sse-and-comet](https://stackoverflow.com/questions/11077857/what-are-long-polling-websockets-server-sent-events-sse-and-comet)

This long-polling endpoint streams new content (e.g. a user posts a comment), content status changes (e.g. user deletes their comment, likes) and moderation changes to content (e.g. moderator approves a piece of content) to a Livefyre App.

The request to Stream API should be ~30 seconds (long-polling) with expected timeout after 30 seconds when no new content streams in.

API Reference: [https://api.livefyre.com/docs/apis/by-category/collections#operation=urn:livefyre:apis:stream1:operations:v3.1:collection:updates:method=get](https://api.livefyre.com/docs/apis/by-category/collections#operation=urn:livefyre:apis:stream1:operations:v3.1:collection:updates:method=get)

Example request: 

`{"timeout":true,"parked":true,"h":"ct245.dsr.livefyre.com"}`

Please note: The `maxEventId` in a Stream API response is the highest Event ID of the updates in this response. Use this value as `lastEventId` path parameter when building the URL of your next Stream API request to get updates occurring after all the updates in this response.

The example below is based on a Comments App:

Comment "First comment" was posted first. "Second Comment" was posted after.

First Comment Stream API response: 

`{"timeout":true,"parked":true,"h":"ct239.dsr.livefyre.com"}`

The `maxEventId` in the response is "1520289700953369" which will be used as `lastEventId` to poll the endpoint to get updates (i.e. Second Comment) occurring after all the updates in this response.

Second Comment Stream API response: 

`{"timeout":true,"parked":true,"h":"ct239.dsr.livefyre.com"}`

The `maxEventID` "1520289700953369" in the response should in turn be used as the `lastEventID` to build the Stream API response for the next update.
