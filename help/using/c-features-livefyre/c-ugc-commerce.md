---
description: Deliver product-specific UGC at specific points of the customer journey to increase purchase intent and conversion using the UGC Commerce feature.
title: UGC Commerce

---

# UGC Commerce{#ugc-commerce}

Deliver product-specific UGC at specific points of the customer journey to increase purchase intent and conversion using the UGC Commerce feature.

Use the UGC Commerce feature to influence purchase intent and conversion on UGC and product detail pages. Speed time to market by seamlessly associating UGC with product inventory. Build brand loyalty by creating community using UGC to highlight authentic customer stories.

AEM Livefyre provides several ways to import product catalog information, including SKU, thumbnail images, price, and product name. Easily manage the association of products with UGC by using AEM Livefyre’s rights requests, auto-stream rule tagging, and moderation workflows.

In addition to influencing purchasing, the capabilities in AEM Livefyre’s UGC commerce offering can be leveraged to drive conversions in other ways including:

* B2B lead generation: place Call-to-action buttons under UGC to capture leads
* B2C App downloads: prompt users to download an App
* Article referrals: link users to articles related to pieces of UGC

Place product call-to-actions alongside UGC to drive conversion. You can:

* Add product-specific UGC at scale to thousands of product detail pages.
* Embed AEM Livefyre’s visualization apps that support UGC commerce capabilities such as Media Wall and Mosaic on product detail pages.
* Use configurable referral tracking codes with an analytics solution to measure the conversions from product CTAs placed on UGC and UGC placed on product detail pages.

AEM Commerce users can seamlessly integrate their existing product catalog into Livefyre to drive user engagement in Livefyre's visualization Apps. Livefyre users who do not use AEM Commerce can manually import their product catalogs into Livefyre. See [Upload Products to Livefyre Using File Upload](/help/using/c-features-livefyre/c-ugc-commerce.md), for more.

Apps that use this feature:

* [Feature Card](../c-about-apps/c-feature-card-app/c-feature-card-app.md#c_feature_card_app). For information on how to use UGC Commerce in a Feature Card, see [Feature Card Customizations](../c-about-apps/c-feature-card-app/c-feature-card-app.md#section_uds_gzm_5y).

* [](../c-about-apps/c-filmstrip-app/c-filmstrip-app.md#concept_jpc_n2j_jbb). For information on how to use UGC Commerce in a Filmstrip, see [Filmstrip Customizations](../c-about-apps/c-filmstrip-app/c-filmstrip-customizations.md#c_filmstrip_customizations).

* [Media Wall](../c-about-apps/c-media-wall-app/c-media-wall-app.md#c_media_wall_app). For information on how to use UGC Commerce in a Media Wall, see [Media Wall Customizations](../c-about-apps/c-media-wall-app/r-media-wall-customizations.md#r_media_wall_customizations).

* [Mosaic](../c-about-apps/c-mosaic-app/c-mosaic-app.md#c_mosaic_app). For information on how to use UGC Commerce in a Mosaic, see [Mosaic Customizations](../c-about-apps/c-mosaic-app/c-mosaic-customizations.md#c_mosaic_customizations).

## Overview: How to use the UGC Commerce Call-to-action Button {#section_s2d_tln_n1b}

1. Create an App with a Call-to-action Button. See [Add a Call-to-action Button to an App](/help/using/c-features-livefyre/c-call-to-action-button.md#task_36190DD1C8204C7793CB7EEA379C2155).
1. Add your product catalog to Livefyre. You can import content in one of two ways:

    * [Import Products into Livefyre Using AEM Commerce](https://helpx.adobe.com/experience-manager/6-4/sites/administering/using/livefyre.html) if you use AEM Commerce.
    * [Upload Products to Livefyre](/help/using/c-features-livefyre/c-ugc-commerce.md) if you do not use AEM Commerce.

1. Associate products with content. You can do this in one of four ways:

    * From the Library. See [Associate Products with Content Using the Library](../c-library/t-associate-products-with-content-using-the-library.md#t_associate_products_with_content_using_the_library)
    * From ModQ. See [Moderate Content Using ModQ](/help/using/c-features-livefyre/c-about-moderation/c-modq.md)
    * From App Content. See [Add a Call-to-action Button to an App](/help/using/c-features-livefyre/c-call-to-action-button.md)
    * From a Stream. See [Stream Rule Options for All Stream Rules](../c-streams/c-stream-rule-options-for-all-stream-rules.md#c_stream_rule_options_for_all_stream_rules).

## Upload Products to Livefyre Using File Upload {#section_n1s_4hz_m1b}

Upload products to use with your Call-to-Action Button to add products to associate with content or to edit and delete existing files.

>[!NOTE]
>
>Uploading a file into a folder with existing files will delete all the files in that folder and overwrite them with the new file.

1. Navigate to **[!UICONTROL Network Settings > Products.]**
1. Create a **[!UICONTROL Product Folder]** or use an existing **[!UICONTROL Product Folder]**.

1. Click on the **[!UICONTROL Product Folder]** to select it.
1. Click the **[!UICONTROL Upload Products]** button.
1. Upload a product file in one of the following formats:

   * Google Products file format
   * Livefyre format (see below)

   Upload a JSON file in the standard format. You can download a template to see an example of the standard format. The following is an example of one product line in a template. It follows the sequence `{"key": "value", "key": "value"}, {"key": "value", "key": "value"}`:

   ```
   {"id": "1", "title": "Flex RN 2017", "isFolder": false, "description": "Flex RN 2017", "price": "$85", "sku": "sku11111", "summary": "This brand is a member of the Sustainable Apparel Coalition", "features": "Cushioning: Lightweight, flexible response", "url": "www.shopping.com/shoes-flex-rn-2017/product/9", "attributes": [{"type": "color", "value": "blue"}
   ```

   The table explains the key and value pairs you need to upload products:

## Key/Value Pairs for Product Catalog Upload Standard Format

|Key|Type|Description|
|--- |--- |--- |
|id|String|Unique ID of the product.|
|oembed|Object|Image attachment `0embed $ref: '../partials/schemas.yaml#/oEmbed'`|
|title|String|Product title.|
|isFolder|Boolean|If true, the product is treated like a folder (for example, mens, womens, etc.).|
|parentId|String|Defines what folder the product is under.|
|description|String|Description of the product.|
|price|String|Value of the product in dollars. For example, '23.36.'|
|sku|String|Stock keeping unit (SKU) of the product.|
|url|String|Link to the product page.|
|enabled|Boolean|A value of True means the product is active.|
|attributes|Array|Types and values that define the product (for example, color, size, etc.). This is an array of objects.</br>**Properties:** </br>type </br>Type: String</br>Description: Color, size </br>value </br>Type: String </br>Description: Green, XS|
|tags|Array|Tags defining categories of content (for example, cars, shoes, etc.). This is an array of strings.|

## ModQ {#section_os1_v4t_n1b}

You can associate content with products from your product catalog in ModQ in line with your existing moderation workflows. For information on how to use UGC Commerce with ModQ, see [Moderate Content Using ModQ](/help/using/c-features-livefyre/c-about-moderation/c-moderate-content-using-app-content.md).

## Streams {#section_qtj_v4t_n1b}

You can automatically associate products to content using stream rules, then publish the content automatically to an App, save it in the Library, or Moderate it using ModQ. For more information on how to use UGC Commerce with Stream Rules, see [Stream Rule Options for All Stream Rules](../c-streams/c-stream-rule-options-for-all-stream-rules.md#c_stream_rule_options_for_all_stream_rules).
