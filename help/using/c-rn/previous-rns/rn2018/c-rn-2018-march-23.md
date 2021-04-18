---
description: Release Notes for the March 23, 2018 release.
title: March 23, 2018
exl-id: 85fd6f79-7fa8-425e-b4c7-2e1635d6ef17
---
# March 23, 2018{#march}

Release Notes for the March 23, 2018 release.

## New Features {#section_syx_mdt_wcb}

The following features are new in the production version of this release:

* **New in Production:** Facebook created a security update to Facebook Login that will cause a customer's Facebook Login to not work correctly. To fix this issue, you must:

    1. Add the following URL to **[!UICONTROL Valid OAuth redirect URIs]** field in Client OAuth Settings. Replace `<networkname>` with your correct network name:
       `https://identity.livefyre.com/<networkname>/api/v1.0/public/profile/social/complete/facebook_fyre`
    
    1. Switch **[!UICONTROL Use Strict Mode for Redirect URI]** to **[!UICONTROL Yes]**.

* **New in UAT:** You can now choose the confidence threshold for smart tags in streams. Setting the precision score (0-100) for tags allows you to control the accuracy of the assets we are retrieving.

## Issues {#section_ehw_ndt_wcb}

The issues in the following tables were resolved in this release.

## Production Release

|  **Issue Type** | **Component** | **Release Note** |
|---|---|---|
|  Bug | Media Wall | Fixed an issue in Media Wall where tags were not clickable when an Instagram post was added from a stream rule. |
|  Bug | ModQ | Fixed an issue with ModQ not loading properly. |
|  Bug | ModQ | Fixed an issue where embedding audio caused ModQ to stop working. |

## UAT Release

|  **Issue Type** | **Component** | **Release Note** |
|---|---|---|
|  Enhancement | Filmstrip | Fixed some issues to make Filmstrip more accessible. |
|  Enhancement | Studio | You can now log into Livefyre using an IMS login. |
