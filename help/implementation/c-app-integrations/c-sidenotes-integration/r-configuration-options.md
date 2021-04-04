---
description: The Sidenotes config object is a JSON object used to specify the content that the Livefyre App renders on the page.
seo-description: The Sidenotes config object is a JSON object used to specify the content that the Livefyre App renders on the page.
seo-title: Sidenotes Configuration Options
solution: Experience Manager
title: Sidenotes Configuration Options
uuid: 067e51e6-9720-4226-a805-c7a07c8cdaa0
exl-id: efebf9e5-6623-4953-a8f6-c58495304ac1
---
# Sidenotes Configuration Options{#sidenotes-configuration-options}

The Sidenotes config object is a JSON object used to specify the content that the Livefyre App renders on the page.

The object contains the following parameters:

|Parameter|Type|Description|
|--- |--- |--- |
|authDelegate|*required* object|New or old style initialized authentication delegate.|
|collectionMeta|*required* object|See collectionMeta token for more information.|
|customIcon|*optional* string|Sets the URL of a custom launcher icon. Defaults to Livefyre bubble.|
|customStyles|*optional* object|Adds custom styles to change the look and feel of Sidenotes. For more information, see Custom Styles.|
|disableStream|*optional* Boolean|If true, disables real-time streaming in this Sidenotes instance (not in other comment streams). Default is false.|
|environment|*optional* string|Specifies the Livefyre UAT environment. The only possible value is `t402.livefyre.com`. For production this parameter must be removed.|
|iconVisibility|*optional* object or string|Defines whether the Sidenotes icon will be visible upon hover or static. If this is a string, it will be used for both versions of the block icon (empty and has Sidenotes). If an object, you must specify each type: {empty: ‘hover’, num: ‘static’}. Default is static.|
|inlineThreads|*optional* boolean|If true, Sidenote threads are inserted directly after the block with which they are associated. Default is false.|
|numSidenotesEl|*optional* object, string, or array|Specifies which element the Sidenotes count widget will decorate. (This widget shows the number of sidenotes on the page and information about Sidenotes.) If the string selector matches more than one element, the first will be chosen. (Uses CSS3 DOM selector spec.)|
|position|*optional* string|Determines the position of the popup when an element that has Sidenotes enabled is clicked. Possible values are ‘smart’, ‘left’, ‘right’, ‘bottom’. Default is ‘smart’ which aligns the popup to the right of the page unless there is not enough space (in which case it will move to below the content).|
|selectors|*required* object, string, or array|Specifies the elements on which launcher icons should appear. (Uses CSS3 DOM selector spec.) If object, includes an “includes” section and an “excludes” section that will apply the CSS selector for any matching includes, and remove any elements matching the excludes. If string, will include any matching elements on the page. If array, lists the elements to include.|
|strings|*optional* object|Adds custom text strings to change any language or text throughout the application. For more information, see Custom Strings.|
|threadContainerEl|*optional* object, string, or array|Specifies an element where the thread of sidenotes will appear. This parameter allows you to reposition the thread. If the string selector matches more than one element, the first will be chosen. (Uses CSS3 DOM selector spec.)|
