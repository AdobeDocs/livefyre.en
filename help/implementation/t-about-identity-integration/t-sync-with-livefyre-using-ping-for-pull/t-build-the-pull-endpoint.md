---
description: Build the pull endpoint to receive and respond to requests for access to your user identity system.
seo-description: Build the pull endpoint to receive and respond to requests for access to your user identity system.
seo-title: Build the Pull Endpoint
solution: Experience Manager
title: Build the Pull Endpoint
uuid: 1703152f-aaa7-4a88-aa33-d9f8957ad42b
exl-id: cc66365b-0d5f-4a0b-954f-ee014e75d4a2
---
# Build the Pull Endpoint{#build-the-pull-endpoint}

Build the pull endpoint to receive and respond to requests for access to your user identity system.

1. Create an HTTPS endpoint that receives Livefyre requests and responds with a JSON object that contains the latest user data.

   >[!NOTE]
   >
   >This endpoint must be accessible. It is also strongly recommended that both requests and responses be sent over the HTTPS protocol.

1. Register the Endpoint with Studio.
