---
description: Count the number of curated social items.
title: Social Counter
exl-id: def7fba4-1c2e-4c7b-84f7-f9ede592d675
---
# Social Counter{#social-counter}

Count the number of curated social items. For a complete list of available endpoints, please see the Livefyre [API Reference](https://api.livefyre.com/docs) section.

The Social Counter API returns counts for matched curation rules in a given collection for intervals over a period of time.

>[!NOTE]
>
>This API is available only for Twitter hashtags.

Social Counter API:

* Resource
* Rule Types
* Response

## Resource {#section_p2s_2hc_11b}

```
GET https://{networkName}.bootstrap.fyre.co/api/v3.0/stats.collections.curate/{query}.json
```

* **networkName:** Your Livefyre provided network name. For example: *labs* in `labs.fyre.co`.
* **query:** The url-safe base64 encoded hash of all the site, article ID, rule-type tuples for which count information should be fetched (pre-encoded)

  ```
  {site ID}:{article ID};{rule-type},  {article ID};{rule-type}|{site ID}:{article ID};{rule-type}
  ```

  >[!NOTE]
  >Query is limited to 10 site, article ID, rule-type tuples. (The previous example would contain 3 tuples.)

* **from** `(optional)` specifies the relative or absolute time period to graph; from specifies the beginning and defaults to 24 hours ago, if omitted.
* **until** `(optional)` specifies the relative or absolute time period to graph; until specifies the beginning and defaults to the current time (now), if omitted.

### Relative Time

|  Abbreviation  | Unit  |
|---|---|
|  s  | Seconds  |
|  min  | Minutes  |
|  h  | Hours  |
|  d  | Days  |
|  w  | Weeks  |
|  mon  | 30 Days (Month)  |
|  y  | 365 Days (Year)  |

Example:

```
https://labs-t402.bootstrap.fyre.co/api/v3.0/stats.collections.curate/MTIzNDU2OnNvbWUtYXJ0aWNsZS1pZDsy.json&from=-7d&until=-6d
```

## Absolute Time {#section_xqr_jgc_11b}

FORMAT: HH:MM_YYYYMMDD

|  Abbreviation  | Meaning  |
|---|---|
|  HH  | Hours (in 24h clock format)  |
|  MM  | Minutes  |
|  YYYY  | 4-Digit Year  |
|  MM  | Month  |
|  DD  | Day  |

Example:

```
https://labs-t402.bootstrap.fyre.co/api/v3.0/stats.collections.curate/MTIzNDU2OnNvbWUtYXJ0aWNsZS1pZDsy.json&from=04:00_20130709 

```

## Rule Types {#section_v53_xqb_11b}

|  Value  | Type  |
|---|---|
|  2  | Twitter  |

Example:

To obtain counts over the last minute for site `123456` and article ID `some-article-id` and rule-type `2`, for example: `123456:some-article-id;2:`

```
curl -XGET "https://labs-t402.bootstrap.fyre.co/api/v3.0/stats.collections.curate/MTIzNDU2OnNvbWUtYXJ0aWNsZS1pZDsy.json&from=-1min" 

```

Example Response:

```
{ 
    "status": "ok", 
    "code": 200, 
    "data": { 
        "123456": { 
            "some-article-id": { 
                "2": [ 
                    [ 
                        2, 
                        1374770460 
                    ], 
                    [ 
                        4, 
                        1374770470 
                    ], 
                    [ 
                        3, 
                        1374770480 
                    ], 
                    [ 
                        1, 
                        1374770490 
                    ], 
                    [ 
                        0, 
                        1374770500 
                    ], 
                    [ 
                        7, 
                        1374770510 
                    ] 
                ] 
            } 
        } 
    } 
}
```
