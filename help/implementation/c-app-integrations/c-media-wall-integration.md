---
description: Create a media wall, with content streaming in real-time.
title: Media Wall
exl-id: 597af7e1-9ada-4893-9071-e17c21ef0d04
---
# Media Wall{#media-wall}

Create a media wall, with content streaming in real-time.

Media Wall allows you to create a real-time social wall for your site. Use the Livefyre JavaScript SDK’s streamhub-wallpackage to display Livefyre social feeds as a visually engaging, full-screen, tiled content experience that’s great for covering live events, hosting photo contests, and powering social sections of your website.

## Integration {#section_jfm_bwb_c1b}

The quickest way to add a Media Wall is to use the built version hosted on Livefyre’s CDN.

First, add [Livefyre.js](https://github.com/Livefyre/Livefyre.js) to your site.

```
<script src="//cdn.livefyre.com/Livefyre.js"></script> 
```

Then, position the element in which the Media Wall will appear.

```
<div id="wall"></div>
```

Finally, use `Livefyre.require` to construct the component.

```
<script> 
Livefyre.require([ 
    'streamhub-wall#5' 
], function(MediaWall) {     
    var wall = window.wall = new MediaWall({ 
        el: document.getElementById("wall"), 
        collection: { 
            "network": "client-solutions.fyre.co", 
            "siteId": "364309", 
            "articleId": "answers-mediawall" 
        } 
    }); 
}); 
</script>
```

You now have a Wall! See this all in action in [this example](https://codepen.io/gobengo/pen/dFwDL).

**Hit an error?** Check to make sure that you’re passing the correct environment parameter. Options include `livefyre.com` (production) or `t402.livefyre.com` (UAT).

>[!NOTE]
>
>Any styling customization of Tweets rendered by your Media Wall App must be done in accordance with Twitter’s [Display Requirements](https://dev.twitter.com/terms/display-requirements).

## Config Options {#section_ucv_qvb_c1b}

`columns`

Allows you to define the number of columns for your Media Wall when constructing your wall. If this option is set, the width of each column will automatically adapt to the Media Wall’s container size, while maintaining the specified number of columns.

```
var wallView = new MediaWall({ 
    el: document.getElementById('wall'), 
    columns: 5 
});
```

`initial`

The number of Content items to render on page load. Defaults to 50.

```
var wallView = new MediaWall({ 
   el: document.getElementById('wall'), 
   initial: 10 
});
```

`minContentWidth`

Allows you to set the minimum (pixel) width for each column within the Media Wall’s container element. (Your Media Wall will automatically select an appropriate number of columns, depending on the width of its container element. By default, the Media Wall’s width divided by the minimum content width (300px, if undefined) determines the number of columns.)

>[!NOTE]
>
>Do not use this option in combination with the columns option.

```
var wallView = new MediaWall({ 
    el: document.getElementById('wall'), 
    minContentWidth: 300 
});
```

`modal`

By default, when there are attachments for a piece of content, Media Walls will display a clickable thumbnail. When clicked, the App will open a modal displaying the photo/video attachment in its entirety. To disable this option, set modal to false.

```
var wallView = new MediaWall({ 
    el: document.getElementById('wall'), 
    columns: 5, 
    modal: false 
});
```

`postButton`

Defines the [!UICONTROL Post Content] button to appear on your Wall. This option requires that you pass in `opts.collection`, and add a Livefyre.js Auth integration to the page.

`postButton` parameters:

* `false` (default): Do not show a Post Content button. (Creates a read-only Media Wall.) 
* `true` (or `LiveMediaWall.postButtons.contentWithPhotos`): Include a button that allows users to add text content, with attached photos. 

* `LiveMediaWall.postButtons.content`: Include a button that allows users to add text content, but not attach photos. 
* `LiveMediaWall.postButtons.photo`: Include a button that allows users to add a photo, but no text.

```
var wallView = new MediaWall({ 
    el: document.getElementById('wall'), 
    collection: collection, 
    postButton: true, 
    minContentWidth: 300 
});
```

`showMore`

Defines the number of Content items to add to the wall when your [!UICONTROL Show More] button is clicked.

```
var wallView = new LiveMediaWall({ 
    el: document.getElementById('wall'), 
    showMore: 10 
});
```

## Styling Config Options {#section_ztv_dvb_c1b}

Media Wall also offers several config options which allow you to customize text color, style, and size. To implement these options, use the following syntax:

```
var wall2 = window.wall2 = new MediaWall({ 
   el: document.getElementById("listView1"), 
   collection: collection, 
   cardBackgroundColor: '#333', 
   textColor: 'magenta', 
   linkColor: 'orange', 
   footerTextColor: 'lime', 
   displayNameColor: 'cyan', 
   usernameColor: 'red', 
   fontFamily: 'Helvetica, Arial', 
   linkAttachmentBackgroundColor: '#555', 
   linkAttachmentBorderColor: '#888' 
}); 

```

For valid input, please see the W3C standards for CSS [Font Family](https://www.w3.org/TR/CSS2/fonts.html#propdef-font-family), [Font Size](https://www.w3.org/TR/CSS2/fonts.html#font-size-props), [Line Height,](https://www.w3.org/TR/CSS2/visudet.html#propdef-line-height) and [Color](https://www.w3.org/TR/css3-color/#colorunits) properties. 

* **bodyFontSize** *(CSS Font Size String)* The font size for content body text.

* **bodyLineHeight** *(CSS Line Height String)* The line height for content body text.

* **buttonActiveBackgroundColor** *(CSS Color String)** The color for the button background on active.

* **buttonBorderColor** *(CSS Color String)** The color for button borders.

* **buttonHoverBackgroundColor** *(CSS Color String)* The color for the button background on hover.

* **buttonTextColor** *(CSS Color String)* The color for the button labels.

* **cardBackgroundColor** *(CSS Color String)* The background color for content cards in the media wall.

* **displayNameColor** *(CSS Color String)* The color for display names in the byline.

* **fontFamily** *(CSS Font Family String)* The font family for body text.

* **footerTextColor** *(CSS Color String)* The color for secondary text (such as the footer text, and the username in the byline).

* **linkAttachmentBackgroundColor** *(CSS Color String)* The background color for link attachments (stacked attachments).

* **linkAttachmentBorderColor** *(CSS Color String)* The border color for link attachments (stacked attachments).

* **linkAttachmentTextColor** *(CSS Color String)* The color for link attachment text.

* **linkColor** *(CSS Color String)* The color for hyperlinks (such as links in body text, and display name links).

* **textColor** *(CSS Color String)* The color for body text.

* **titleFontSize** *(CSS Font Size String)* The font size for content titles.

* **titleLineHeight** *(CSS Line Height String)* The line height for content titles.

* **sourceLogoColor** *(CSS Color String)* The color for the source logo.

* **usernameColor** *(CSS Color String)* The color for the usernames in the byline.
