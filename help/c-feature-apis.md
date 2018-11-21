---
description: Automate the process using the Feature APIs
seo-description: Automate the process using the Feature APIs
seo-title: Feature APIs
title: Feature APIs
uuid: 08cc5e2e-d3c8-4ed0-b5cf-2c8f22e0bbba
index: y
internal: n
snippet: y
---

# Feature APIs{#feature-apis}

Automate the process using the Feature APIs

Use the Feature APIs to automate the process by which content is Featured. For example, when creating a Live Blog or Comment App, Feature all content posted by a selected moderator to steer the conversation, and establish consistency within the stream.

Livefyre offers both Feature and Unfeature APIs.

## Feature {#section_jpw_nqw_xz}

**Resource**

```
POST: https://{networkName}.quill.fyre.co/api/v3.0/collection/<collectionId>/feature/<commentId>/?lftoken=<base64userToken>
```

​Enter the user token for your selected moderator.

**Post Data**

```
{value: <number>} 

```

The value will be used to sort featured content, largest to smallest (10 will appear before 1 in the featured content list). This value defaults to **now** in epoch time, so featured comments will typically be sorted newest to oldest.

**Example Response**

```
{"status": "ok", "code": 200, "data": null} 

```

>[!NOTE]
>
>The data field is not yet in use.

## Unfeature {#section_knh_mqw_xz}

**Resource**

```
POST: https://{networkName}.quill.fyre.co/api/v3.0/collection/<collectionId>/unfeature/<commentId>/?lftoken=<base64userToken>
```

Enter the user token for your selected moderator.

**Example Response**

```
{"status": "ok", "code": 200, "data": null} 

```

>[!NOTE]
>
>The data field is not yet in use.

