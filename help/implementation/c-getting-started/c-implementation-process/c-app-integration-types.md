---
description: When you implement Livefyre Apps, the style of implementation depends on your use case. This page explains the features for the three ways you can create an App.
title: CMS App Integrations
exl-id: 7590e247-87cc-470e-bab6-e61a19221dbd
---
# CMS App Integrations{#cms-app-integrations}

When you implement Livefyre Apps, the style of implementation depends on your use case. This page explains the features for the three ways you can create an App.

Livefyre integration is agnostic to any CMS and User Profile and Auth platform. Implement Livefyre in one or more ways, depending on your use-case and requirements.

You can use traditional integration to create customized AEM components.

## CMS App Integration Type Overview

|Type|Development Requirement|Features|Pros|Limitations|
|--- |--- |--- |--- |--- |
|App Designer|Very Low|Create JS embeds in Studio to add to pages without a developer <br>Limited Styling and Configurations available </br>Use case: Single Use Pages (event coverage, campaigns, hubs)|Able to get an App up and running in a short amount of time. <br>Configurations can be done by a non-technical member. <br>Easy on the fly changes to configurations|Must create an App using Livefyre Studio first <br>Not automated|
|Livefyre.js|Medium|Integrate Apps into the JavaScript of your pages <br>Use case: Reusable templates (editorial content, product reviews)|Use the full suite of App customizations and configurations <br>Automates the process to dynamically instantiate Apps from within your CMS onto your pages|Need a developer up front.|
|SDK APIs|Advanced|Retrieve your content from Livefyre to use for custom applications <br>Customize front-end beyond out supported offering <br>Use case: Data/Analytics integrations and custom front-end apps|Full power over the look and feel of App|Requires development up front. <br>Higher level of dev effort to implement.|
