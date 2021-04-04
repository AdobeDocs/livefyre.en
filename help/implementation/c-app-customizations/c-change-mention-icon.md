---
description: Change the icon displayed for Livefyre users in the @mention pulldown menu.
seo-description: Change the icon displayed for Livefyre users in the @mention pulldown menu.
seo-title: Change @mention Icon
solution: Experience Manager
title: Change @mention Icon
uuid: a395f4ff-a774-454a-8d94-4a3371d8cc2c
exl-id: e078ef7f-7f16-4f5d-9152-95ae7fe7e4bd
---
# Change `@mention` Icon {#change-mention-icon}

Change the icon displayed for Livefyre users in the `@mention` pulldown menu.

Change the Livefyre icon used in the `@mention` pulldown menu to an icon of your choosing, allowing you to indicate your community members with your own icon.

## Example

To change this icon, add the following CSS to your stylesheet. Replace &lt;*your resource*&gt; url with the URL of the image selected to replace the default Livefyre badge.

```
.fyre-editor-container .fyre-editor-toolbar > .fyre-mention-menu .fyre-mention-item .fyre-mention-item-livefyre { 
    background: url(<your resource url>) no-repeat center; 
    background-position: 0px 0px; 
    background-size: 22px 22px; 
}
```
