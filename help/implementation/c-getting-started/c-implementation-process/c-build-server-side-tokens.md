---
description: A guide for building collectionMeta and auth tokens.
seo-description: A guide for building collectionMeta and auth tokens.
seo-title: Build Server Side Tokens
solution: Experience Manager
title: Build Server Side Tokens
uuid: 8313f26e-5ceb-414e-a61a-480bb7a8ba66
exl-id: f709b79e-9236-443e-b862-c7d281815d91
---
# Build Server Side Tokens{#build-server-side-tokens}

A guide for building collectionMeta and auth tokens.

Building the tokens that Livefyre uses to validate requests ensures that only you can make updates to your Livefyre network.

## CollectionMeta Token

Learn how to build a token to create new and display existing conversations.

## Auth Token

Learn how to build a token for authenticating users, a necessary step in the integration process if you’re not using Janrain Capture for user management.

## User Auth Token {#section_l5l_hwt_bbb}

This section describes how to generate the UserAuth JSON Object that creates the User Authentication token required to log users into your Apps.

To create the token, use your preferred language library to pass in the following parameters:

|  Parameter | Type | Description |
|---|---|---|
|  networkName | String *required* | The name of the Livefyre network (provided by Livefyre). |
|  networkKey | String *required* | The secret key for this specific network (provided by Livefyre). |
|  userId | String *required* |The ID of the user logging in as stored in your user management system (only alphanumeric, dash, underscore, and dot characters are allowed: `[a-zA-Z0-9_-.]`). **Note:** The userId must be unique. |
|  expires | Integer *required*  |When the token should expire from now (in seconds). **Note:** This value can also be passed as a float. The JSON web token produced will store this value in UNIX epoch time. |
|  displayName | String *required* | Text to identify this user in the UI and in comments. (Maximum number of characters: 50.) |
