---
description: Implement Sidenotes using .js implementation.
seo-description: Implement Sidenotes using .js implementation.
seo-title: Sidenotes Implementation
solution: Experience Manager
title: Sidenotes Implementation
uuid: aa13852e-e2b0-4a86-97cd-d08ab5e2cfab
exl-id: 07a68677-c67e-4128-8cb7-c5fb9e0ecc60
---
# Sidenotes Implementation{#sidenotes-implementation}

## Implement Sidenotes using .js implementation

To implement this feature, pass in a 1-1 object mapping of the strings you wish to override to the Javascript configuration object. If you don’t provide a field, then the default text will be used.

### Example

```
var customStrings = { postAsButton: "New Post As Text", postEditButton: "New Post Edit Text"};networkConfig["strings"] = customStrings; fyre.conv.load( networkConfig, [convConfig], function(){});
```
