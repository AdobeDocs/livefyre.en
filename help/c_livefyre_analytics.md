---
description: null
seo-description: null
seo-title: Use Livefyre with Other Analytics Tool
solution: Experience Manager
title: Use Livefyre with Other Analytics Tool
uuid: 93de14c2-9f54-43b6-b5d4-380ee1a44b95
index: y
internal: n
snippet: y
translate: y
---

# Use Livefyre with Other Analytics Tool

You can use analytics tools to gather data on user interactions with Livefyre Apps. You can use Adobe Analytics or a tool of your choice. For information on how to use Adobe Analytics with Livefyre, see [](#c_livefyre_analytics).



To use Livefyre with a tool of your choice (not Adobe Analytics), follow the procedure outlined on this page. 
## Step 1: Set up event handler {#section_ngm_gzl_pdb}

Set up an event handler on pages where you use Livefyre Apps. This allows you to collect data from the Apps on that page that you can use for analytics.

Add Livefyre.js to a page to set up the event handler. Livefyre.js loads asynchronously. To reduce file size and improve load performance, analytics are not available immediately. You must poll the analytics object until data is available. Place this script anywhere on the page or bundle it within your own compiled scripts.

```
/** 
 * Handler for Livefyre analytics batch events. 
 * @param {Array.<string>} events Array of events that have been fired since 
 * the last batch send. 
 */ 
function analyticsHandler(events) { 
  // Send to analytics 
  console.log(events); 
} 
 
var attempts = 0; 
 
function pollForAnalytics() { 
  if (Livefyre && Livefyre.analytics) { 
    Livefyre.analytics.addHandler(analyticsHandler); 
    return; 
  } 
  if (attempts === 10) { 
    return; 
  } 
  attempts++; 
  setTimeout(pollForAnalytics, 500); 
} 
 
pollForAnalytics(); 

```

## Step 2: Implement handler function

Once Livefyre.analytics functionality is available on the page, implement the analyticsHandler function to send the received events to the analytics provider of your choice.

1. The analytics handler receives an array of events that must be iterated through and sent individually or as a batch, if your provider supports it.
1. Map the event data received by the handler to a format that your analytics provider requires. You can see the list of analytics events and descriptions in [](c_livefyre_analytics_events.md#table_n24_1kd_4cb).
1. Send the data to your analytics provider.
