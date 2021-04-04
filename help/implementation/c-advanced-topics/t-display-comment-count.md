---
description: Grab the post and comment counts for certain collections to display on your index pages.
seo-description: Grab the post and comment counts for certain collections to display on your index pages.
seo-title: Display Comment Count
solution: Experience Manager
title: Display Comment Count
uuid: 0f39b25e-11e0-4945-be71-55fb4798b6c7
exl-id: 03c911f0-1fdd-4d5c-9262-9ff7485b7b14
---
# Display Comment Count{#display-comment-count}

Grab the post and comment counts for certain collections to display on your index pages.

Livefyre’s `CommentCount.js` allows you to fetch the content counts for collections on your site. Although Apps will show the comment count for the current collection, having these counts syndicated across your site can be useful. This feature is especially useful if you don’t persist content in your database (or if your CMS database is not synced with Livefyre).

1. Load the JavaScript.

   To use `CommentCount.js`, first embed the JavaScript file in the `<head>` section of the page or template where you’d like to use it.

   ```
   <script 
      type="text/javascript" 
      data-lf-domain="{network name (domain.fyre.co)}" 
      src="//cdn.livefyre.com/libs/commentcount/v1.0/commentcount.js"> 
   </script>
   ```

1. Bind the HTML Element.

   Once the script is loaded, it will attempt to find other elements on the page with a class name of `livefyre-commentcount`. For each of these elements, the script will look for `data-lf-site-id` and `data-lf-article-id` HTML attributes, and will use these to fetch content from Livefyre and update each element with the latest value.

   For example, the following element would be updated:

   ```
   <span class="livefyre-commentcount" data-lf-site-id="{site_id}" data-lf-article-id="{article_id}"> 
   0 Comments  
   </span>
   ```

   >[!NOTE]
   >
   >The `CommentCount.js` code checks for a numeric value to update with the actual count. Be certain to include a numeric value between the tags.

   **Example 1** (Using the URL as the article ID):

   ```
   <span class="livefyre-commentcount" data-lf-site-id="311458" data-lf-article-id="https://mikesoldner.com/blog.php">  
   0 Comments  
   </span>
   ```

   **Example 2** (Using a numbered system as the article ID):

   ```
   <span class="livefyre-commentcount" data-lf-site-id="311458" data-lf-article-id="25"> 0 Comments </span>
   ```

1. Configure Options.

   For more control over how the content counts are replaced, call `LF.CommentCount()` and pass in an object containing the configuration options. Make sure to call the function after all of the elements that need to be replaced are in the DOM. The best place to call this method is in the footer, so it happens when the DOM is loaded, but prior to document and window ready events.

   We allow the following configuration options:

* **replacer:** Function or Regex used to replace the text of each content count.

* **function:** Used to do the replacement on each element. The function’s arguments are:

  **element:** The HTML element that is being updated.
  **count:** The content count for this element.

* **regex:** Used to determine which part of the element’s text should be replaced by the count.

  **Example**:

   ```
      <script type="text/javascript"> LF.CommentCount({ 
        replacer: function(element, count) { 
            element.innerHTML = count +' Comment'+ (count === 1 ? '' : 's'); 
        } 
    }); 
   </script>
   ```

   >[!NOTE]
   >
   >Use the replacer to customize or internationalize the comment count message.
