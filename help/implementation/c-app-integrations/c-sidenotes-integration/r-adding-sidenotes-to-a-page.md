---
title: Adding Sidenotes to a Page
description: Adding Sidenotes to a Page
exl-id: 3ec089d0-3d51-4918-b510-d30ef645c9c2
---
# Adding Sidenotes to a Page {#adding-sidenotes-to-a-page}

Livefyre provides several configuration options to position Sidenotes on your page:

* The Selectors option defines the elements on which Sidenotes should appear.
* Anchors represent elements which can be sidenoted.
* The custom thread container allows you to define where the Sidenotes thread will be located in relation to the sidenoted content.
* The Sidenotes count option allows you to display the number of Sidenotes added at the given location.
* Use multiple `ConvConfig` objects to add Sidenotes to several stories on a single page.

## Selectors {#section_wyj_4sv_sy}

The selectors option enables Sidenotes to find content on the page. The value for this option allows you to dynamically determine the elements that will be used. It can be a selector string (such as ‘#content p, #content img’), a jQuery object (such as `$(‘#content’)`), an array of DOM elements, or an object with two properties: include and exclude. The Sidenotes App will then use either the specified elements or the matching elements on the page. If include and exclude properties are used, Sidenotes will first parse the page to find all elements on the include property, then remove any elements found on the exclude property.

## Anchors {#section_ehq_psv_sy}

Anchors represent an element whose content can be sidenoted. An anchor element can contain text or an image. The selectors option that is passed during App construction will determine the anchor elements.

## Anchor IDs {#section_rsb_rsv_sy}

Anchors on the page are identified using a `data-lf-anchor-id`.

To set the ID for an anchor yourself, add the attribute `data-lf-custom-anchor-id` to the element that you would like to map to an anchor. This is helpful in cases where the auto-detection of anchors would fail.

For example, if you plan to use a different URL for the desktop and mobile versions of an image, two different URLs might be mapped to different anchors. If, instead, your HTML supplies a `data-lf-custom-anchor-id` that is the same on both mobile and desktop, then the image element will be treated as a single anchor.

Anchors have a type that is determined dynamically, but can also be explicitly set using the `data-lf-custom-anchor-type` attribute.

>[!NOTE]
>
>The enumeration number value must be used.

Available types are:

* **Text:** 1
* **Image:** 2
* **Media:** 3
* **Rich:** 4

See [updateAnchors method](/help/implementation/c-app-integrations/c-sidenotes-integration/update-anchors-method.md) for more on how to use the `updateAnchors` method to add Sidenote content to the page dynamically.

## Custom Thread Container {#section_jdh_btv_sy}

Use the `threadContainerEl` option to specify a location for a Sidenotes thread, other than the default position. By default, when an anchor is activated, the Sidenotes will appear next to or below the relevant content. To change this default, use the `threadContainerEl` to specify the element where the thread should appear.

This value for this option works the same as the selectors option, except only the first valid element will be used.

## Sidenotes Count {#section_pld_ntv_sy}

Use the `numSidenotesEl` option to embed an optional Sidenotes count widget on your page. This option accepts the same input as the selectors option but will use only the first valid element in the input array.

The widget will decorate the provided or matched element, and will include the Sidenotes input icon, the number of Sidenotes entered at this position, and a help icon.

Clicking on the widget will display a popover with a short explanation of Sidenotes and how to use them.

Both the explanation and the example text are configurable using custom strings ( `questionExplanation` and `questionMockText`, respectively). The appearance of the count widget and the popover may also be configured using custom styles ( `numSidenotes` and `numSidenotesPopover`, respectively).

## Adding Multiple Sidenotes Collections to a Single Page {#section_pjl_ptv_sy}

Livefyre allows you to add multiple Sidenotes Collections to a single page. For example, if the page includes three news stories, you may wish to include three separate iterations of the Sidenotes App. To do this, you must define a separate `ConvConfig` object for each instance of Sidenotes you wish to build. For example: 

```
<html> 
   <head> 
      <script src="//cdn.livefyre.com/Livefyre.js"></script> 
   </head> 
<body> 
   <h2>Story #1</h2> 
   <div id="story1"> 
      <p class="sidenotes">stuff #1</p> 
      <p class="sidenotes">more stuff #1</p> 
   </div> 
   <hr /> 
   <h2>Story #2</h2> 
   <div id="story2"> 
      <p class="sidenotes">stuff #2</p> 
      <p class="sidenotes">more stuff #2</p> 
      <p class="sidenotes">more and more stuff</p> 
   </div> 
   <hr /> 
   <script type="text/javascript"> 
      var convConfig_story1 = { 
         network: '<Your Network>', 
         siteId: '<Site ID>', 
         articleId: '<Your Article ID>', 
         selectors: '#story1 > p.sidenotes', 
         collectionMeta: '<First collectionMeta>' 
      }; 
  
      var convConfig_story2 = { 
         network: '<Your Network>', 
         siteId: '<Site ID>', 
         articleId: '<Your Second Article ID>', 
         selectors: '#story2 > p.sidenotes', 
         collectionMeta: '<Second collectionMeta>' 
      }; 
  
      Livefyre.require(['sidenotes#1', 'auth'], function(Sidenotes, auth) { 
         new Sidenotes(convConfig_story1); 
         new Sidenotes(convConfig_story2); 
         auth.delegate({ 
            login: function (callback) { 
               callback(null,{livefyre: '<Login Token>'}); 
            } 
         }); 
      }); 
   </script> 
</body> 
</html>
```
