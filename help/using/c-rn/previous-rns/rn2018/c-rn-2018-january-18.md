---
description: Release Notes for the January 18, 2018 release.
seo-description: Release Notes for the January 18, 2018 release.
seo-title: January 18, 2018
solution: Experience Manager
title: January 18, 2018
uuid: 8141f431-c154-4c8f-bbcd-b7c712fe5f7d
exl-id: aaf49dc9-64eb-4354-8bcb-04039fa25f10
---
# January 18, 2018{#january}

Release Notes for the January 18, 2018 release.

## Production Release

|  **Issue Type** | **Component** | **Release Note** |
|---|---|---|
|  Bug | Apps | Fixed bug that prevented Avatars to be rendered correctly when a jpeg file was being used. |
|  Bug | ModQ | Fixed a bug for S1 customers to allow filtering by Collections in ModQ. |
|  Bug | Streams | Fixed a bug that broke a stream rule when the language filter was set as "none." |
|  Bug | Streams | Fixed a bug that prevented Youtube stream rules from being saved. |
|  Bug | Streams | Fixes a bug where users could create wrongfully formatted geo entries in stream rules and save them, which would make the stream fail. Now, users can no longer save badly formatted geo tags. |
|  Bug | Studio | Fixed an issue that prevented some users from logging into Livefyre. |

## UAT Release

|  **Issue Type** | **Component** | **Release Note** |
|---|---|---|
|  Bug | Library | Security bug fix. All authentication calls are now made using the HTTPS protocol instead of HTTP. |
|  Enhancement | Smart Tags | Streamed content is now automatically smart tagged by Adobe Sensei as it is saved to a folder or published to an app. |
|  Bug | Streams | Fixed an issue where Instagram stream rules did not recognize Japanese characters. |
|  Enhancement | Streams | Customers can now use the logical operators ( ANY, ALL, NOT) to create detailed smart-tag filters in streams that curate much more accurate content. For example if I use the hashtag #himalyas I can select to show only images that include "snowy" "mountains".  |
|  Bug | Studio | Fix to a bug which showed special characters in names as HTML. |
