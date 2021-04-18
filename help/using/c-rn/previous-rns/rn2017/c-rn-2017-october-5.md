---
description: Release Notes for the October 5, 2017 release.
title: October 5, 2017
exl-id: 6e39a86e-82dd-47ff-ad68-2b483f8b1921
---
# October 5, 2017{#october}

Release Notes for the October 5, 2017 release.

## Production Release

|  **Issue Type** | **Component** | **Release Note** |
|---|---|---|
|  Bug | Livefyre Identity | Customers using Livefyre identity to login were experiencing issues seeing or updating their avatars when posting to commenting apps. This has been fixed now, as avatars are now visible and available for updating.  |
|  Bug | Rights Management | Fixed a bug with displaying long usernames in the Rights Modal tab. |
|  Enhancement | Streams | Added the ability to hit the tab key in a Streams text field to complete a search term. |

## UAT Release

|  **Issue Type** | **Component** | **Release Note** |
|---|---|---|
|  Enhancement | Filmstrip | When a customer deploys a film strip app, newly streamed UGC will have a "new" label next to it to quickly identify them. |
|  Enhancement | Filmstrip | Filmstrip is a brand new visualization App, primarily designed to showcase UGC in e-commerce scenarios, such as product pages or transactional websites. Film Strip horizontally aligns UGC to be displayed as a camera roll, one piece at the time. End users can navigate Filmstrip by clicking the side arrows to scroll through the content available. |
|  Enhancement | Library | Files uploaded into the library by a customer will be automatically rights granted. This is a helpful feature when the users have turned on the "require rights granted" filter in their apps.  |
|  Enhancement | Livefyre Identity | Customers can now use their Github credentials to login into LIvefyre Identity and participate in our commenting apps. |
|  Bug | Rights Management | Fixed a bug that allowed insertion of unicode characters in Rights Request messages to bypass validation. |
|  Enhancement | SAFE | Minor improvements added to SAFE Spam detection. |
|  Bug | Service | Users without valid emails have emails constructed for them. Fixed an issue with production logs where the system did not send emails to these users. |
|  Enhancement | Studio | Updated the Livefyre Help link in the top navigation bar. |
|  Enhancement | UGC Commerce | As a customer I can now create a single Livefyre app (Mosaic, FilmStrip or Media Wall) and embed it in multiple product pages, that dynamically filters the appropriate UGC for each product page (example UGC with shoes for a Shoe product page). |
|  Enhancement | UGC Commerce | Customers can now manually upload a google product catalogue into Livefyre studio using a JSON file export. This enables the customer to pair UGC with products from that catalogue and visualize them in our commerce enabled apps.  |
|  Enhancement | UGC Commerce | Customers can select which product folders they want to use when filtering their E-commerce app by product ID. For example I want my new filmstrip to appear in my women's shoes and women bags product pages, therefore I will select only the "Women's shoes collection" and "Women's bags" product folders. |
|  Enhancement | UGC Commerce | Livefyre customers can now filter the UGC published to their apps only if they have been rights granted. For example a customer can curate and publish a selection of items, but those items will only be rendered in the app once they have been rights granted by the author. This is particularly important for E-commerce use cases, where the UGC is used for commercial purposes. |
