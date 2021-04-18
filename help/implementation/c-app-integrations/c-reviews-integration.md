---
description: Allow customers to rate and review your product offerings.
title: Reviews
exl-id: 2f10646e-59c4-459c-ae1b-749f951a06d2
---
# Reviews {#reviews}

Allow customers to rate and review your product offerings.

Reviews allows members of your community to contribute star ratings and qualitative reviews for any product or service.

## Integration {#section_kk5_15b_c1b}

To integrate a Reviews App, follow the procedure for Integrating a Conversation App. See [Embed an App](/help/implementation/c-livefyre-identity-comp/t-using-studio-to-connect-your-social-apps-to-your-livefyre-implementation.md). The following is an example of an embedded Reviews App.

### Example

```
var networkConfig = { 
   network: "client-solutions-uat.fyre.co" 
}; 
  
var convConfig = { 
   siteId: '304059', 
   articleId: 'sh_col_22_1373478370_reviews', 
   el: 'livefyre-comments', 
   app: 'reviews', 
   ratingSummaryEnabled: true, 
   maxRating: 5, 
   collectionMeta: 'eyJhbGciOiAiSFMyNTYiLCAidHlwIjogIkpXVCJ9.eyJ1cmwiOiAiaHR0cDovL3d3dy5kaXJlY3R2LmNvbS9wZXJzb24vQW5uYS1QYXF1aW4tYjJGU0wwZHJLM051YldjOS1yZXZpZXdzIiwgInNpdGVJZCI6ICIzMDQwNTkiLCAiYXJ0aWNsZUlkIjogInNoX2NvbF8yMl8xMzczNDc4MzcwX3Jldmlld3MiLCAidHlwZSI6ICJyZXZpZXdzIiwgInRpdGxlIjogIlRCX1BhcXVpbl9yYXRpbmdzX3Jldmlld3MifQ.hes3KMwygCG-fFDQlkaB-XlxGjW6-iZ68xA4RRGqUl0' 
}; 
  
Livefyre.require(['fyre.conv#3'], function (Review) { 
   new Review(networkConfig, [convConfig], function (reviewWidget) {}); 
   auth.delegate({ 
      login: function (callback) { 
         callback(null,{livefyre:'<userauthtoken>'}); 
      }, 
   }); 
});
```

As noted in the Building `CollectionMeta` section, `CollectionMeta` is an encoded JSON object. In the above example, the JSON object takes the following format before it’s JWT encoded:

```
{ 
"url": "https://www.directv.com/person/Anna-Paquin-b2FSL0drK3NubWc9-reviews",  
"siteId": "304059",  
"articleId": "sh_col_22_1373478370_reviews",  
"type": "reviews",  
"title": "TB_Paquin_ratings_reviews" 
}
```

## convConfig Object {#section_pzv_ytb_c1b}

If you’ve already completed the Getting Started section you should be familiar with convConfig object. To enable Reviews, update the convConfig with the following fields: 

* **alwaysShowEditor** *optional* boolean: By default, the reviews editor appears only after the user presses the “write review” button. Set this parameter to true to always display the editor.

* **app** *required* string: The App name to use for reviews. Must be “reviews“.

* **defaultSort** *optional* string: Allows you to select the default sort option for Reviews. Possible values are: mostHelpful, highestRated, lowestRated, newest, and oldest.

* **disableTitle** *optional* boolean: Disables and hides the title field in the reviews editor, which is required and visible by default. Default is true.

* **enableHalfRating** *optional* boolean: Used to enable half ratings on the default star selection module. Default is true.

* **hideShowReviewButton** *optional* boolean: Controls whether the [!UICONTROL Show My Review] button will be displayed. Set to true to allow your users to select whether to show or display their own reviews.

* **maxRating** *optional* integer Used to set the number of stars that are shown on the default star selection module. Default is 5. This can be configured up to 100.

* **ratingSummaryEnabled** *optional* boolean: Used to show the rating summary view above the Reviews App. This must be enabled to use the ratingSummaryDelegate. Default is true.

## Review Collection Metadata {#section_k1s_sqb_c1b}

* **type:** *required* string: Defines the Collection type. Must be `reviews`.

* **ratingDimensions** *optional* array: An array of strings for each type of dimension that this Collection will use. If this is not specified, only 1 dimension will be allowed.

  For example, to allow users to rate your product on ‘design’, ‘features’, and ‘performance’, set the array to: `ratingDimensions: [‘design’, ‘features’, ‘performance’]`

* **ratingSubparts** *optional* integer: Number of partitions to display in the review’s text box. The subpart labels are passed in with the parameter as illustrated below.

  >[!NOTE]
  >You must define labels for each subpart.

* **ratingSubpartsIds** *optional* array: Allows you to define an ID for each subpart in your Ratings Collection, which may be used to target these subpart elements in your CSS and JavaScript. When users post reviews, each `ratingSubpart` will have the “ `data-lf-subpart-id`” attribute on it, populated with this ID.

>[!NOTE]
>
>To use `ratingSubpartsIds`, the `ratingSubparts` param must also be defined, and the length of the two arrays must match.

```
networkConfig["strings"] = { 
   ratingSubpartPlaceholders: ['Pros...', 'Cons...'], 
   ratingSubpartTitles: ['Pros:', 'Cons:'], 
   ratingSubpartIds: ['pros', 'cons'], 
   reviewStreamTitle: 'Description:' 
} 
fyre.conv.load(networkConfig, [{ 
   app: 'reviews', 
   ratingSubparts: 2, 
    ... // More conv config settings 
}]);
```

>[!NOTE]
>
>If you’re using `ratingDimensions`, you MUST use the `ratingSelectionDelegate`, `ratingDisplayDelegate`, and `ratingSummaryDelegate` (if you want to show the rating summary).

## Reviews Customization {#section_khz_xmb_c1b}

### Configure Star Images

To change the image for full stars, the class is `goog-ratings-star`. Change the background image to whatever image you’d like. By default, stars are 28 by 28 pixels.

### Configure Star Images with Half Stars

With half stars, there are two classes, one for each side of the star. The left side of the half star is `fyre-rating-half-odd` and the right side is `fyre-rating-half-even`. By default, half stars are 28 by 14 pixels.

### Configure the Tooltip Values for Stars

To configure the tooltip values for the stars, follow the custom text described in String Customizations. Once you have that set up, use the key `ratingValues` and the value an array that contains the tooltip strings. If you have half stars disabled, the number of elements in the array should be the same as `maxRating` (above). If you have half stars enabled, the number of elements should be 2x `maxRating`. The first element in the array corresponds to the left-most star (or half star) element and continues left to right.

### Toggle the 'Show My Review' Option

To toggle the [!UICONTROL Show My Review] option on or off, target the `hideShowReviewButton` parameter in the App configuration.

### Show the Text Editor by Default

The reviews editor appears only after the user presses the [!UICONTROL write review] button. To show this form by default, target the `alwaysShowEditor` parameter in the App configuration.
