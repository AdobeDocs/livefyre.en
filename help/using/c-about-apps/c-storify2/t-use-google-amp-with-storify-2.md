---
description: Use Livefyre APIs to add Google AMP functionality to your Storify 2 page to keep the content interactive and SEO-friendly.
title: Use Google AMP with Storify 2
exl-id: 2fee8655-ac9f-484e-a042-9b7ac7151fcc
---
# Use Google AMP with Storify 2{#use-google-amp-with-storify}

Use Livefyre APIs to add Google AMP functionality to your Storify 2 page to keep the content interactive and SEO-friendly.

To use Google AMP with Storify 2, you must create a page for your Storify 2 App with Google AMP markup.

The AMP version of the App requests updates from the original page (use the **pollInterval** parameter in the **amp-live-list** API to set the interval for update requests). To ensure that visitors on your AMP page get the most up-to-date content quickly, keep a low-cache TTL on your Storify 2 AMP pages.

Non-image assets (for example, videos) included as posts in a Storify 2 App must use HTTPS as specified by the AMP specification. AMP URLs that use Google Cloud Content Delivery Network (CDN) use HTTPS.

To use Google AMP with Storify 2:

1. Create an AMP-validated template on your site.
1. Use one or more of the following Google AMP APIs to customize your Google AMP page:
   1. [amp-iframe](https://www.ampproject.org/docs/reference/components/amp-iframe) to customize the Storify 2 display
   1. [amp-live-list](https://www.ampproject.org/docs/reference/components/amp-live-list) to customize the time interval for updates
   1. [amp-social-share](https://www.ampproject.org/docs/reference/components/amp-social-share) to add a social sharing button
1. Include the contents of the following Storify 2 AMP page into the CSS for your Storify 2 page within the `<style amp-custom>` tag: [https://cdn.livefyre.com/libs/liveblog-v2-component/amp.min.css](https://cdn.livefyre.com/libs/liveblog-v2-component/amp.min.css)
1. Include the contents of the following Storify 2 AMP markup API into your Google AMP template: `https://api.livefyre.com/app-service/v4/bootstrap/{{APP_ID}}/amp` where {{APP_ID}} is the App ID for the Storify 2 App in Livefyre Studio.
   1. The only query parameter is **pollInterval**, which is the interval in which the app will check for updates (set in milliseconds).
   1. The URL includes content from the most recent posts (including Tweets, videos, etc.)
   1. The publisher page needs to get content from this URL as often as you want the Google AMP page to be updated.
