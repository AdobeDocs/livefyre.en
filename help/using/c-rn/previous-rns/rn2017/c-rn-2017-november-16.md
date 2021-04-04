---
description: Release Notes for the November 16, 2017 release.
seo-description: Release Notes for the November 16, 2017 release.
seo-title: November 16, 2017
solution: Experience Manager
title: November 16, 2017
uuid: e7d09640-d2c1-4d23-8fa6-ecc90d0b2daa
exl-id: 167b8c7d-f2fb-4735-9681-d349646ec3eb
---
# November 16, 2017{#november}

Release Notes for the November 16, 2017 release.

## Production Release

|  **Issue Type** | **Component** | **Release Note** |
|---|---|---|
|  Bug | AEM, Library | Fixed a bug with no results being returned when using Tag and Rating search in Library. |
|  Bug | Apps | Fixed an issue where the feature tag did not display on a single card App. |
|  Bug | Carousel | Fixed an issue where Carousel wasn't appearing in Designer. |
|  Bug | Comments | Fixed inaccurate comment counts in comments apps.  |
|  Enhancement | Feature Card | The Feature Card App has the all the commerce functionality enabled.  |
|  Enhancement | Filmstrip | We have added resizing options for Filmstrip so that the user can have more control on how the images look in the App.  |
|  Bug | Hot Threads | Fixed error messages from Hot Threads to make them more secure. |
|  Enhancement | Library | Customers have the ability to delete the Smart Tags applied by our AI system. Once deleted they won't see those tags in search results. |
|  Bug | Library | Fixed an issue where an image did not displaying properly after adding it to the library from a social search. |
|  Bug | Library | Fixed an issue with creating folders being slow. |
|  Bug | Library | Users can now post .mov files to Collections. |
|  Bug | Library | Images with special characters in the title would not upload into the library, this has now been fixed. |
|  Enhancement | Library | We have updated our "relevance" Ranking algorithm when a user searches for smart tags, so when a user toggles the "relevance" sort in library search, the new ranking algorithm is engaged. This new ranking algorithm takes into consideration, smart tag precision scores, number of stars assigned by user and age of the document. The objective is to make the tag search experience more accurate for the user.  |
|  Enhancement | Library | When a customer saves an asset to the library, Livefyre employs Adobe Sensei machine learning technology to add tags that describe what is in the image of the asset automatically. This enables the user to search for those tags in the system.  |
|  Enhancement | Library | When a customer saves an image based asset to the library, Livefyre will now automatically tag it using Adobe AI technology, extracting features, categories and aesthetic properties from the system. This allows the user to search the library by what is inside of the images, not just the text.  |
|  Bug | Livefyre Identity | Avatars were not loading correctly for Microsofts implementation of LF identity, this has been fixed. |
|  Bug | ModQ | Fixed an issue where streams premoderation and ModQ were not displaying all content properly. |
|  Enhancement | Settings | Customers can now visit our privacy policy and Adobe's terms of service in a footer in Settings.  |
|  Enhancement | Streams | Fixed a bug for pre-moderation of email based stream rules.  |
|  Enhancement | Streams | Added the ability to filter stream content by language. |
|  Enhancement | Users | Added the ability to use .png files for user avatars. |

## UAT Release

|  **Issue Type** | **Component** | **Release Note** |
|---|---|---|
|  Bug | App Manager | Fixed an issue with the App tag search in App Manager.  |
|  Bug | Library | Fixed an issue that prevented adding stars for multiple pieces of content at a time in the Asset Library.  |
|  Bug | Studio | Fixed an issue that prevented some users from logging into Livefyre. |
