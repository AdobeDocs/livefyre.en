---
description: Use available CSS classes to customize your Apps’ display.
title: CSS Classes
exl-id: 605f2c47-13f7-4535-90b1-c53cbf548534
---
# CSS Classes{#css-classes}

Use available CSS classes to customize your Apps’ display.

Available for Chat, Comments, Live Blog, Reviews, and Sidenotes.

Use CSS to customize your Livefyre Apps for a more complete integration with your page, by simply overriding the default App CSS with your own stylesheet. This section describes available CSS customizations.

* [Editor CSS](#c_css_classes/section_edx_prh_xz)
* [Sorting Options CSS](#c_css_classes/section_btq_4rh_xz)
* [Comment CSS](#c_css_classes/section_mlv_nrh_xz)
* [Featured Comments CSS](#c_css_classes/section_m2v_mrh_xz)
* [Archived Comments CSS](#c_css_classes/section_bs5_lrh_xz)
* [Comment Notifier CSS](#c_css_classes/section_dy4_krh_xz)
* [Storify CSS Classes](../c-app-customizations/c-storify-css-classes.md#c_storify_css_classes)

## Editor CSS {#section_edx_prh_xz}

Use these classes to change the post editor interface.

|  Class  | Description  |
|---|---|
|  .fyre-comment-count  | The text displaying the number of comments.  |
|  .fyre-login-bar  | The bounding box that contains the login bar and options.  |
|  .fyre-live-container  | The bounding box around the number of people listening and their avatars.  |
|  .fyre-editor  | The bounding box around the .fyre-login-bar, .fyre-live-container and the text area where users write their comments.  |
|  .fyre-stream-sort  | The bounding box around the sorting options.  |

You can also edit styles in the App configuration itself, including the editor field background color, and the font color, size, and family of the text that appears inside the editor.

To customize the comment editor, add the editorCss:{} object to fyre.conv.load() and include your desired styling. For example, to update the editor with your custom CSS:

```
fyre.conv.load(networkConfig, [{ 
   siteId: LF_siteId, 
   el: 'livefyre', 
   articleId: LF_articleId, 
   collectionMeta: #CollectionMeta 
   editorCss: { 
      background: '#ccc', 
      color: 'red', 
      font: '30px "Helvetica Neue", Helvetica, Arial, Geneva, sans-serif' 
   } 
}]);
```

## Sorting Options CSS {#section_btq_4rh_xz}

|  Class  | Description  |
|---|---|
|  .fyre-stream-sort  | The entire sorting options div.  |
|  .fyre-stream-sort-newest  | The option “Newest”.  |
|  .fyre-stream-sort-oldest  | The option “Oldest”.  |
|  .fyre-stream-sort-bar  | The separator bar between the options.  |
|  .fyre-stream-sort-selected  | The currently selected sorting option.  |

HTML Structure:

```
<div class="fyre-stream-sort"> 
   <a href="#" class="fyre-stream-sort-newest fyre-stream-sort-selected">Newest</a>  
   <span class="fyre-stream-sort-bar"> | </span> 
   <a href="#" class="fyre-stream-sort-oldest">Oldest</a> 
</div>
```

Hide the ‘|’ separating the sorting options.

```
.fyre-stream-sort .fyre-stream-sort-bar { 
    display: none !important; 
}
```

## Comment CSS {#section_mlv_nrh_xz}

|  Class  | Description  |
|---|---|
|  .fyre-comment-author-tag- *`custom tag name`* | Livefyre will create a CSS class in this format for each user tag added through Livefyre’s Studio, [Profile Sync](/help/implementation/t-about-identity-integration/t-sync-with-livefyre-using-ping-for-pull/t-sync-with-livefyre-using-ping-for-pull.md). This class may be used to style the background for any content posted by user accounts including that tag.  |
|  .fyre-tag-content-icon- *`tag name`* | Livefyre will create a CSS class in this format for each content tag added through Livefyre [Studio](/help/implementation/c-app-customizations/c-adding-users-to-groups.md). This class may be used to style any content to which you have added the tag.  |
|  .fyre-comment-user  | The bounding box that contains the user profile picture.  |
|  .fyre-comment-username  | The username.  |
|  .fyre-moderator  | The moderator bounding box.  |
|  .fyre-comment  | Bounding box around the comment text/link.  |
|  .fyre-comment-article  | The bounding box for the entire comment content.  |
|  .fyre-comment-date  | The tag attached to the “time since posted” element.  |
|  .fyre-comment-media  | The bounding box around the media content.  |
|  .fyre-comment-actions  | The bounding box around the available actions to take on a comment.  |
|  .fyre-comment-like  | The bounding box around the “Like” link.  |
|  .fyre-comment-reply  | The bounding box around the “Reply” link.  |

## Featured Comments CSS {#section_m2v_mrh_xz}

>[!NOTE]
>
>All Comment CSS classes may also be applied to Featured Content.

|  Class  | Description  |
|---|---|
|  .fyre-featured-content-wrapper  | The container div for the reader.  |
|  .fyre-featured-header  | The leading title bar.  |
|  .fyre-featured-header-icon  | The header’s quill icon.  |
|  .fyre-featured-title  | The header text.  |
|  .fyre-featured-body  | The container div for featured content in the reader.  |
|  .fyre-featured-quote  | The quote icon that begins each content item.  |

## Archived Comments CSS {#section_bs5_lrh_xz}

>[!NOTE]
>
>All content CSS classes may also be applied to archived content.

|  Class  | Description  |
|---|---|
|  .fyre-archive-stream-title  | The “From the Archive” text.  |
|  .fyre-archive-stream-title-icon  | The logo for the “From the Archive” header.  |

## Comment Notifier CSS {#section_dy4_krh_xz}

These classes allow you to customize the Livefyre Comment Notifier.

|  Class  | Description  |
|---|---|
|  .fyre-notification  | The div for the list item (both new and archive content).  |
|  .fyre-notifier  | The wrapper for the contents of the Notifier.  |
|  .fyre-notifier-archive  | The wrapper for all new content other than the most recent post.  |
|  .fyre-notifier-avatar  | The image for the avatar.  |
|  .fyre-notifier-avatar-container  | The container div for the user avatar. Allows you to define positioning.  |
|  .fyre-notifier-avatar-shading  | The shading for the avatar div.  |
|  .fyre-notifier-banner  | The container for the Notifier’s preview content, which displays the user avatar and a content snippet for the most recently posted item.  |
|  .fyre-notifier-base  | The container for the information part of the Notifier, which lists the number of new comments, the Notifier caption, and the close button.  |
|  .fyre-notifier-base-close  | The container div for the close button (x) for the Notifier.  |
|  .fyre-notifier-base-shadow  | The shading for the Notifier base.  |
|  .fyre-notifier-caption  | The text displayed for the notifier. ‘New Comment(s)’ by default.  |
|  .fyre-notifier-close  | A button which closes the notifier.  |
|  .fyre-notifier-container  | The container for the Notifier, includes both the banner and the base.  |
|  .fyre-notifier-counter  | The container for the number listed in the Notifier.  |
|  .fyre-notifier-list  | The container for the most recent piece of content.  |
|  .fyre-notifier-message  | The first ~30 characters of the content displayed.  |
|  .fyre-notifier-message-container  | The container div for the header message.  |
