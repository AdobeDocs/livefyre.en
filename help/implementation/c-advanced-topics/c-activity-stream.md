---
description: Learn how monitor and store the user-generated content flowing through the Livefyre system.
title: Activity Stream
exl-id: 4a552034-96e4-4f1c-9965-3495992005f1
---
# Activity Stream {#activity-stream}

Learn how monitor and store the user-generated content flowing through the Livefyre system.

Use the Activity Stream API to consume user generated data flowing through the Livefyre system on your network or site. For example: use data from this API to update your search indices based on ratings, or to manage users’ badges in a 3rd party system based on their activity.

Activity Stream API:

For a complete list of available endpoints, please see the Livefyre API Reference section.

## Resources {#section_aql_n4l_b1b}

There are two endpoints, one for the staging environment, and one for production.

### Staging

```
GET https://bootstrap.t402.livefyre.com/api/v3.1/activity/ 

```

### Production

```
GET https://bootstrap.livefyre.com/api/v3.1/activity/ 

```

### Parameters

* **resource:** *string* A URN of the object for which you are requesting activity data.

* **since:** *integer* A 64-bit integer representing the the ID of the last event you received. Specify ‘0’ if you have no prior data.

## URN Strings {#section_skl_q4l_b1b}

Examples:

* **urn:livefyre:** `example.fyre.co` The activity stream for `example.fyre.co`.
* **urn:livefyre:** `example.fyre.co:site=54321` The activity stream for site 54321 under the `example.fyre.co` network.

## Token Policies {#section_nwh_c5j_11b}

The Activity Stream API uses an OAuth Bearer Token for authentication. Bearer Tokens are part of the OAuth 2.0 specification, and officially described [here](https://tools.ietf.org/html/rfc6750#section-1.2).

A token contains several things:

* Who created the token.
* Who was given a token.
* A time at which it’s no longer valid.
* The thing we are operating on.
* A list of permissions that have been granted.

### Steps

The steps to create an OAuth Bearer Token include:

* Create a map/dictionary containing the issuer, audience, subject, expiration and scope.
* Use the JWT library, with your secret, to encode a JWT token.
* Add “Authentication: Bearer ” to your HTTP request.

The code sample below demonstrates the above steps in Python:

```
import time 
import jwt 
  
# network data goes here: 
network = "timeout-0.fyre.co" 
network_secret = "...replaceme..." 
  
# api URN 
api_urn = "urn:livefyre:api:core=GetActivityStream" 
  
# expires in 10 seconds 
expiration = int(time.time() + 10) 
  
network_urn = "urn:livefyre:" + network 
  
data = dict(iss=network_urn, aud=network_urn, sub=network_urn, scope=api_urn, exp=expiration) 
  
token = jwt.encode(data, key=network_secret)
```

Where the bearer token keys are defined as follows:

* **iss** *(Issuer)* An entity with the authority to generate tokens. This may be Livefyre, a site or a network. (For a note to be late to school, it’s your parent.)
* **aud** *(Audience)* The person for whom this token was generated. If you are creating the token yourself it is the site or network.
* **sub** *(Subject)* The subject for which permissions are to be granted. For example if you’re operating on a collection, the subject must be the identifier for the collection. (In the note from school example, it’s you.)
* **exp** *(Expiration)* A point in time which the token is no longer valid.
* **scope** *(Scope)* This is a list of the permissions granted on the subject. “Late for school” is an example. The name of an API is another example.

## Example {#section_dhl_ytj_11b}

```
curl -H "Authorization: Bearer <BEARER TOKEN>" https://bootstrap.livefyre.com/api/v3.1/activity/?resource=&since=
```

## Response {#section_gs2_stj_11b}

```
{ 
"code": 200,  
"data": { 
  "annotations": {},  
  "authors": {  
      /** "a set of every author who generated activity within this window" */ 
      "_up1770425@livefyre.com": { 
        "avatar": "https://gravatar.com/avatar/68c789597150d3e941769a5c0a0c4249/?s=50&d=https://avatars-qa.fyre.co/a/anon/50.jpg",  
        "displayName": "ross_pfahler",   
        "id": "_up1770425@livefyre.com",  
        "profileUrl": "https://www.qa-ext.livefyre.com/profile/1770425/",  
        "tags": [],  
        "type": 1 
      },  
  ... 
  },  
  "collections": {  
      /** "a set of every collection for which an activity was generated" */ 
      "2486601": { 
        "articleIdentifier": "75",  
        "id": "2486601",  
        "site": "290596",  
        "title": "Live Blog",  
        "url": "https://orangesaregreat.com/..." 
      }, 
  ... 
  },  
  /** "the maximum event ID for this window" */ 
  "maxEventId": 1383508243715211, 
  "states": {  
      /** "a set of messages (comments, reviews, etc) for which activity  
           was generated in this window, represents the compiled 
           'state' of the object including visible actions on that object 
           (up-votes, likes, and etc.)" */ 
      "3ad6480eb00c4895b29b7a972380f489@livefyre.com": { 
          "collectionId": "2486685",  
          "content": { 
              "annotations": { 
                "rating": [ 90 ], /** "this object is a Rating (4.5)" */ 
                "vote": [ 
                    { 
                      "author": "_up1792695@livefyre.com",  
                      "collectionId": "2486685",  
                      "value": 1 
                    } 
                ] 
              },  
              "attachments": [  
              /** "a list of oembeds; the body of this Rating included  
                  this Youtube video" */ 
                { 
                  "author_name": "mauricio890",  
                  "author_url": "https://www.youtube.com/user/mauricio890",  
                  "height": 480,  
                  "html": "<iframe width=\"854\" height=\"480\" src=\"https://www.youtube.com/embed/pmMAw5a7POU?autoplay=1&feature=oembed\" frameborder=\"0\" allowfullscreen></iframe>",  
                  "link": "https://www.youtube.com/watch?v=pmMAw5a7POU",  
                  "provider_name": "YouTube",  
                  "provider_url": "https://www.youtube.com/",  
                  "thumbnail_height": 360,  
                  "thumbnail_url": "https://i1.ytimg.com/vi/pmMAw5a7POU/hqdefault.jpg",  
                  "thumbnail_width": 480,  
                  "title": "Napoleon Dynamite dance scene",  
                  "type": "video",  
                  "url": "https://www.youtube.com/watch?v=pmMAw5a7POU",  
                  "version": "1.0",  
                  "width": 854 
                } 
              ],  
              // "who authored the content" 
              "authorId": "_up1793160@livefyre.com",  
              "bodyHtml": "<p><strong>Pros:</strong>Boom</p><p><strong>Cons:</strong>Goes</p><p><strong>Description:</strong>The dynamite:</p><p><a href=\"https://www.youtube.com/watch?v=pmMAw5a7POU\" target=\"_blank\" rel=\"nofollow\">https://www.youtube.com/watch?v=pmMAw5a7POU</a><br/></p>",  
              // "UNIX timestamp" 
              "createdAt": 1383257354,  
              "id": "3ad6480eb00c4895b29b7a972380f489@livefyre.com",  
              // "non-empty only if this were a reply" 
              "parentId": "", 
              // "UNIX timestamp"  
              "updatedAt": 1383257356  
          },  
          // "the event ID of this state." 
          "event": 1383369320554187,  
          "lastVis": 3,  
          "source": 0,  
          "type": 0,  
          // "Object visibility: 0 = deleted, 1 = everyone, 2 = bozo,  
          // 3 = owner + admins (e.g. premod)" 
          "vis": 1  
      },  
      "5943789": { 
          "collectionId": "2486688",  
          "content": { 
            "annotations": { 
                // "posted by a moderator" 
                "moderator": true  
            },  
            "authorId": "_up1792872@livefyre.com",  
            "bodyHtml": "<p>This is a regular comment from a moderator</p>",  
            "createdAt": 1383372338,  
            "id": "5943789",  
            "parentId": "",  
            "updatedAt": 1383372338 
          },  
          "event": 1383372338732492,  
          "lastVis": 0,  
          "source": 5,  
          "type": 0,  
          "vis": 1 
      },  
      "863c616a2c0c44239feed0914c282d7c@livefyre.com": { 
          "collectionId": "2486685",  
          "content": { 
              "id": "863c616a2c0c44239feed0914c282d7c@livefyre.com" 
          },  
          "event": 1383371303805767,  
          "lastVis": 1,  
          "source": 0,  
          "type": 0,  
          "vis": 0 // "0 = deleted; this object was removed" 
      },  
  ... 
},  
"meta": { 
  // "this describes position in the stream" 
  "cursor": {  
    // "maximum number of objects returned in a single call through this API" 
    "limit": 50,  
    // "the final position in the stream, and from where data should be requested" 
    "next": 1383508243715211, 
    // "the initial position (the 'since' parameter value in this request)" 
    "self": 0  
  } 
},  
"status": "ok" 
} 

```

A response with new data since the last request:

```
{ 
    "code": 200,  
    "data": { 
        "annotations": {},  
        "authors": {},  
        "collections": {},  
        "maxEventId": -1,  
        "states": {} 
    },  
    "meta": { 
        "cursor": { 
            "limit": 50, 
            /** "indicates there is no data beyond 1383508243715211" */  
            "next": null, 
            "self": 1383508243715211 
        } 
    },  
    "status": "ok" 
}
```

## Notes {#section_hj3_crj_11b}

* A successful call to the API will yield an HTTP 200 status code. All other status codes should be considered errors.
* If non-null, use the value from `data.meta.cursor.next` as the `since` parameter of your next request.
* If the value from `data.meta.cursor.next` is null, it means there is no new data to consume. You should re-request later with the same `since` value to see if new data has arrived.
* As a matter of practice, you should immediately request more data if the `data.meta.cursor.next` value is non-null.
* Approximately two hours worth of recent data is available through this API in production.
* You should set up your processes to poll this endpoint frequently on cronjob in order to avoid missing data. An interval of five minutes should be perfectly adequate for most implementations.
