---
description: null
seo-description: null
seo-title: Use Livefyre with Adobe Analytics And Dynamic Tag Manager (DTM)  lk  xavvn   vefyre with Adobe Analytics And Dynamic Tag Manager (DTM)
uuid: 9a1c25c0-c474-46ff-82ac-e89357007c7f
exl-id: a866782d-fca6-48bf-9fb8-5080e396919b
---
# Use Livefyre with Adobe Analytics And Dynamic Tag Manager (DTM){#use-livefyre-with-adobe-analytics-and-dynamic-tag-manager-dtm}

Set up Adobe Analytics and Dynamic Tag Manager (DTM) to collect data for Livefyre Apps.

## Step 1: Set up Events in Adobe Analytics {#section_iks_kgd_4cb}

Map Livefyre events to one or more Custom Success Events in Adobe Analytics Report Suite Manager.

For more information on Report Suite Manager, see [Report Suite Manager](https://docs.adobe.com/content/help/en/analytics/admin/manage-report-suites/report-suites-admin.html).

1. Log in to Adobe Analytics as an Administrator User.
1. Open Adobe Analytics Admin Report Suite Manager.
1. Create a new Report Suite or choose an existing one.
1. Edit the report suite by clicking on the report suite to modify, then navigate to **[!UICONTROL Edit Settings > Conversion > Success Events]**.
1. Map the Livefyre events to one or more Custom Success Events.

## Step 2: Set up Conversion Variables

Map Livefyre conversion variables (eVars) to conversion variables in Adobe Analytics Admin Report Suite Manager. Conversion variables act like a sorting function to determine how you plan to identify data gathered from Livefyre events.

1. In the Report Suite Manager click **[!UICONTROL Edit Settings > Conversion > Conversion Variables]**.
1. Choose the custom conversion variables (eVars) to use and map them to the Livefyre conversion variables. To map a Livefyre conversion variable to a custom conversion variable:
* Enable the conversion variable
* Name the conversion variable
* Give the conversion variable a type
1. Save the custom conversion variables.

## Step 3: Use DTM to Add your Report Suite with Livefyre Events {#section_t15_2hd_4cb}

Add Adobe Analytics to DTM to get Analytics working. To do this, create a new property and tool and add the new report suite with Livefyre events to the property. For more information on DTM, see [DTM](https://docs.adobe.com/content/help/en/dtm/using/c-overview.html).

You do not need to perform this step if you already have a property or tool set up for the report suite you set up with Livefyre events.

1. In DTM, create or edit an existing property. 
1. Create or edit an existing Adobe Analytics tool. 
1. If an existing Adobe Analytics Tool does not exist, click the **[!UICONTROL Add a Tool]** button.
Set the following parameters for the tool:

   * Set **[!UICONTROL Tool Type]** to **[!UICONTROL Adobe Analytics]**.
   * Enable **[!UICONTROL Automatic Configuration]**.
   * Enable **[!UICONTROL Authenticate via Marketing Cloud]**.
1. Add or confirm the name of the report suite with Livefyre events to the **[!UICONTROL Report Suites]** field.

## Step 4: Set up a Page Load Rule to Set Up Analytics Handling {#section_jfj_j3d_4cb}

Set up a Page Load Rule to pull in all the data. The Page Load Rule allows you to put custom javascript in the rule that records the event when the page loads.

>[!NOTE]
>
>Do not use Event Based Rules or Direct Call Rules.

1. In DTM, select **[!UICONTROL Rules]** tab.
1. Click **[!UICONTROL Page Load Rules]**.
1. Click on the **[!UICONTROL Create New Rule]** button.
1. Open the **[!UICONTROL Conditions]** section by clicking on the **[!UICONTROL Plus]** button.
1. Trigger the rule. Choose **[!UICONTROL DOM Ready]** or **[!UICONTROL Onload]** trigger types if you want to delay or implement the rule asynchronously.
1. (Optional) Add additional parameters to limit the pages that display Livefyre Apps. For more information about additional configuration options, see [DTM](https://docs.adobe.com/content/help/en/dtm/using/c-overview.html).
1. Under **[!UICONTROL Javascript/ Third Party Tags]**, click the **[!UICONTROL Non-sequential]** tab, then click **[!UICONTROL Add New Script]**.
1. Select **[!UICONTROL Sequential HTML]** as the script type.
1. Add the following script into the code editor and click **[!UICONTROL Save Code]**.

   The following script calls the `livefyre_analytics` direct call rule after the Livefyre JavaScript loads. The following script example checks every 400ms to see if `livefyre.analytics` is on the page. After the page loads, livefyre.analytics sends out tracking information.

   ```
   /** 
   * Poll for Livefyre.analytics object to exist since it gets loaded via the 
   * Livefyre.js JavaScript file. Depending on the timing, this could already 
   * exist or need a little time. 
   */ 
   function pollForAnalytics() {  
   if (Livefyre.analytics) { 
     _satellite.track('livefyre_analytics'); 
       return true; 
     } 
     setTimeout(pollForAnalytics, 400); 
   } 
   setTimeout(pollForAnalytics, 400);
   ```

1. Click **[!UICONTROL Save Code]**.
1. Click **[!UICONTROL Save Rule]**.

## Step 5: Create a Direct Call Rule to Construct the Adobe Analytics Mapping Configuration for Livefyre {#section_gvp_b1g_pdb}

There are other ways to implement Livefyre with DTM by using custom events, Adobe Analytics UI fields within DTM, and data elements. This document uses custom Javascript to accomplish the same effect.

1. In DTM select the **Rules** tab and then click on **Direct Call Rules**.
1. Click on the **Create New Rule** button.
1. Name the new rule **Livefyre Analytics**.
1. Expand the **conditions** configuration area.
1. In the **String** field, enter `livefyre_analytics`.
1. Expand the Javascript / 3rd Party Tag section and click on the **Add New Script** button.
1. Enter **Livefyre Analytics Config** into the **Tag Name** input box.
1. Select **Non-Sequential Javascript**.
1. Enter the following Livefyre configuration code into the code editor and click on the **Save Code** button.

   ```
   var s = _satellite.getToolsByType('sc')[0].getS(); 
    
   var evarMap = {  
     appId: 'eVar81',  
     appType: 'eVar82' 
   }; 
    
   var eventMap = { 
     FlagCancel: 'event82',  
     FlagClick: 'event82',  
     FlagDisagree: 'event82',  
     FlagOffensive: 'event82',  
     FlagOffTopic: 'event82',  
     FlagSpam: 'event82',  
     Like: 'event82', 
     Load: 'event81',  
     RequestMore: 'event82',  
     ShareButtonClick: 'event82',  
     ShareFacebook: 'event82',  
     ShareOnPostClick: 'event82',  
     ShareTwitter: 'event82',  
     ShareURL: 'event82',  
     SortStream: 'event82',  
     TwitterLikeClick: 'event82', 
     TwitterReplyClick: 'event82',  
     TwitterRetweetClick: 'event82',  
     TwitterUserFollow: 'event82' 
   }; 
     
    function trackLivefyreEvent(data) {  
     var event = eventMap[data.type]; 
     console.log('Track:', data.type, event); 
     
     if (!event) { 
       console.warn(data.type, 'is not mapped   to an event in AA');  
       return; 
     } 
     var vars = ['events'];  
     switch (event) { 
       case 'event82': s.eVar83 = data.type;  
         vars.push('eVar83');  
         break; 
       default: 
     } 
       ['generator', 'evars'].forEach(function (type) {  
       var obj = data[type]; 
       for (var d in obj) { 
         if (obj.hasOwnProperty(d) && evarMap[d]) {  
           s[evarMap[d]] = obj[d];  
           vars.push(evarMap[d]); 
         } 
       } 
     }); 
     s.linkTrackVars = vars.join(',');  
     s.linkTrackEvents = event;  
     s.events = event; 
      
     console.log('linkTrackVars:',  s.linkTrackVars);  
     console.log('linkTrackEvents:',  s.linkTrackEvents);  
     console.log('events:', s.events); 
     s.tl(); 
     } 
     ]

     /** 

   ```

   * Adds an analytics handler for all analytics events from Livefyre. For each event, it sets the data on a global object and then dispatches the event. 

   ```
   */ 
   function addAnalyticsHandler() {  
     Livefyre.analytics.addHandler(function (events) { 
       (events || []).forEach(function (data) {  
         console.log('Event handled:', data.type);  
         trackLivefyreEvent(data); 
       }); 
     }); 
   } 
   addAnalyticsHandler();  
   ```

1. Click on **Save Rule**.

## Step 6: Approve changes for Page Load Rule {#section_pxc_11t_ycb}

1. Go to **[!UICONTROL Approvals]** tab.
1. Click **[!UICONTROL Approve]**.
1. Click **[!UICONTROL Yes, approve]** to confirm your approval.
1. Go to **[!UICONTROL Overview > Publish Queue]**.
1. Select the Rule to publish.
1. Click **[!UICONTROL Publish Selected]**.
1. Click **[!UICONTROL Publish]** to confirm that you want to publish.

## Script {#section_xkb_vft_mcb}

The following sample code maps the specific eVars to available Livefyre eVars. The Livefyre conversion variable ( `eVar`) name (for example, `appId`) maps to the name you set up in the Report Suite Manager (for example, `eVar81`). Change the `eVar` names in this script to the custom conversion variables.


```

var s = _satellite.getToolsByType`('sc')[0]`.getS(); 
var evarMap = { 
  appId: 'eVar81', 
  appType: 'eVar82' 
};

```

The following sample code maps the specific events you set up in the Report Suite Manager with available Livefyre events. In this example, `event82` is set up as any user interaction event without differentiating which kind of user interaction event (for example, liking or sharing content). This is an efficient way to record all user interaction information in a block. You can also map the events in the DTM Analytics UI with Data Element referencing.

```
var eventMap = { 
  FlagCancel: 'event82',  
  FlagClick: 'event82',  
  FlagDisagree: 'event82',  
  FlagOffensive: 'event82',  
  FlagOffTopic: 'event82',  
  FlagSpam: 'event82',  
  Like: 'event82', 
  Load: 'event81',  
  RequestMore: 'event82',  
  ShareButtonClick: 'event82',  
  ShareFacebook: 'event82',  
  ShareOnPostClick: 'event82',  
  ShareTwitter: 'event82',  
  ShareURL: 'event82',  
  SortStream: 'event82',  
  TwitterLikeClick: 'event82', 
  TwitterReplyClick: 'event82',  
  TwitterRetweetClick: 'event82',  
  TwitterUserFollow: 'event82' 
};
```

The following sample states that if there isn't an event in this list, don't do anything. You do not need to modify this section of code.

```
function trackLivefyreEvent(data) {  
  var event = eventMap[data.type]; 
  console.log('Track:', data.type, event); 
   
  if (!event) { 
    console.warn(data.type, 'is not mapped to an event in AA');  
    return; 
  }
```

The following code differentiates the event types that `event82` records. The conversion variable, `eVar83` records the type of user interaction, and the script sets up `eVar83` to separate the user interaction data by type. So `eVar83` allows you to break out the recorded data into specific types of user interactions.

```
  var vars = ['events'];  
  switch (event) { 
    case 'event82': s.eVar83 = data.type;  
      vars.push('eVar83');  
      break; 
    default: 
  } 
   
  ['generator', 'evars'].forEach(function (type) {  
    var obj = data[type]; 
    for (var d in obj) { 
      if (obj.hasOwnProperty(d) && evarMap[d]) {  
        s[evarMap[d]] = obj[d];  
        vars.push(evarMap[d]); 
      } 
    } 
  }); 
   
  s.linkTrackVars = vars.join(',');  
  s.linkTrackEvents = event;  
  s.events = event; 
   
  console.log('linkTrackVars:', s.linkTrackVars);  
  console.log('linkTrackEvents:', s.linkTrackEvents);  
  console.log('events:', s.events); 
   
  s.tl(); 
}
```

The following code sample adds a handler to listen to all the events that happen. It uses the page load rule on load, waits for events to exist, then sets up handler for all events from the App and tracks them. You do not need to modify this code.

```
/** 
* Adds an analytics handler for all analytics events from Livefyre. For each event, it sets the data on a global object and then dispatches the event. 
*/ 
function addAnalyticsHandler() { 
  Livefyre.analytics.addHandler(function (events) { 
    (events || []).forEach(function (data) { 
      console.log('Event handled:', data.type); 
      trackLivefyreEvent(data); 
    }); 
  }); 
}
```

## More Info

For more information on the topics discussed on this page, see:

* [Report Suite Manager](https://docs.adobe.com/content/help/en/analytics/admin/manage-report-suites/report-suites-admin.html)
* [DTM](https://docs.adobe.com/content/help/en/dtm/using/c-overview.html)
* [Rules](https://docs.adobe.com/content/help/en/dtm/using/resources/rules/create-rules.html)
* [Livefyre.js](/help/implementation/c-livefyre.js.md)
