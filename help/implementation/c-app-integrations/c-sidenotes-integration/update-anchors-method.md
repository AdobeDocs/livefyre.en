---
description: The core Livefyre library used to power Livefyre on your site.
seo-description: The core Livefyre library used to power Livefyre on your site.
seo-title: updateAnchors Method
solution: Experience Manager
title: Livefyre.js
uuid:
exl-id: 5f60ce54-5669-4768-912d-c1b13946d8b8
---
# updateAnchors Method {#updateAnchorsMethod}

Use the updateAnchors method to add sidenoted content to the page dynamically. 

This method is useful for pagination, or in other cases where sidenote-able content is added to the page dynamically. This method defines new anchors for the matched elements, and takes a single argument: newSelectors.

**newSelectors**. The selectors to add to Sidenotes. This may be a selector string, a jQuery object, or an array of elements (any of the types accepted by the selectors argument passed during app construction).
Format:

```
app.updateAnchors(newSelectors);
```

Example:

```
var app = new Livefyre.Sidenotes(convConfig);// Load more contentapp.updateAnchors('#content');
```
