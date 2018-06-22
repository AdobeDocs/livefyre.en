---
description: To custom style content for User Groups, you must first add a User Tag to the account, then style the content using CSS.
seo-description: To custom style content for User Groups, you must first add a User Tag to the account, then style the content using CSS.
seo-title: Applying Custom Styles
solution: Experience Manager
title: Applying Custom Styles
---

# Applying Custom Styles

For each user tag added through Studio or Ping for Pull, Livefyre will create two CSS classes, both of which may be used to style the group’s content.

When converting User Tags to CSS classes:

* Livefyre creates two classes: fyre-author-tag-***&lt;your_group&gt;*** and fyre-tag-author-***&lt;your_group&gt;***. Both may be used to style the content.
* Any spaces included in the tag will be converted to underscores. For example: ‘Favorite User’ will become favorite_user.
* Unicode characters included in group names will not be converted, and will appear as Unicode in the class names. For example: User group ‘modérateur’ will become fyre-comment-author-tag-modérateur.
Once your user groups have been created, use Livefyre’s CSS classes to apply custom styling for the content.

## Style content for Moderators (and Owners) {#section_vjv_2cv_xz}

  *
  Use the CSS class .fyre-moderator.
  
  >[!NOTE]
  >
  >Owners, because they are also Moderators, will have this class applied to their content in the stream as well.
  
  *
  Create a CSS rule to show or style a badge for the Group:
  
  ```
  .fyre-moderator { 
   font: 13px "Helvetica Neue", Helvetica, Arial, Geneva, sans-serif; 
   text-decoration: none; 
   color: #404040; 
   padding-left: 28px; 
   padding-top: 4px; 
  }
  ```
  
## Style content for User Groups {#section_ghn_s1v_xz}

Create a CSS rule to show or style a badge for the Group:


```
&lt;span class="fyre-comment-author-tag fyre-comment-author-tag-writer fyre-comment-plus" data-fyre-author-tag="staff"&gt;Staff Writer&lt;/span&gt;
```

```
.livechat-comments-container .fyre .fyre-comment-wrapper .fyre-comment-author-tag, .comments-container .fyre .fyre-comment-wrapper .fyre-comment-author-tag { 
 display: inline-block !important; 
 background: #603url('/etc/designs/site/images/comments-icon-staff.8db5be91.png?1438807177') no-repeat left center !important; 
 padding-right: 3px !important; 
 padding-left: 20px !important; 
 text-transform: uppercase !important; 
 font-weight: bold !important; 
 font-size: 11px !important; 
 border-radius: 0 !important; 
 color: #ffffff !important; 
}
```
Use the CSS class fyre-author-tag-***&lt;your_group&gt;*** or fyre-tag-author-***&lt;your_group&gt;*** to style the font and background for each item posted from an Account associated with the selected tag.

```
.fyre-comment-author-tag-&lt;your_group&gt; .fyre-comment-author-tag { 
 font: 10px "Helvetica Neue", Helvetica, Arial, Geneva, sans-serif; 
 text-decoration: none; 
 color: #404040; 
 padding-left: 28px; 
 padding-top: 4px; 
}
```
