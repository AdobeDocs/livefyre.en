---
description: Change the size, width, and interaction options of the Map app.
seo-description: Change the size, width, and interaction options of the Map app.
seo-title: Feature Card Customizations
solution: Experience Manager
title: Feature Card Customizations
uuid: dd43c076-027f-42c8-be2e-7d863d4e3976
exl-id: b907885a-211d-4628-9955-5f1a5ec577cf
---
# Feature Card Customizations{#feature-card-customizations}

Change the size, width, and interaction options of the Map app.

<!-- 
r_feature_card_customization.dita
 -->

Feature Card Apps include only standard customizations:** [!UICONTROL Theme]**, Brand color, Font family, and Font size.

You can customize Feature Cards using:

* **[!UICONTROL Style]** and **[!UICONTROL Config]** options for all Apps in the **[!UICONTROL App Designer]**. See Customizing Apps for details on the standard **[!UICONTROL Style]** and **[!UICONTROL Config]** options for all Apps in the **[!UICONTROL App Designer]**.

* Integration tools. See App Integrations for more on how to customize Apps using Integration Tools.
* **[!UICONTROL Call-to-action button]** You can use the Call-to-action button with a product catalog to direct users to a product or to your site for further action.

  * **[!UICONTROL Call-to-action button]** Switch the toggle to on to display the Call-to-action button.
  * **[!UICONTROL Require rights to display products]** Switch the toggle to on to require that the content owner has granted rights for the content before a Call-to-action button appears for the content.

    >[!NOTE]
    >
    >The content displays even if rights are not granted for the content, but the Call-to-action button will not display with the content unless rights for the content are granted.

  * **[!UICONTROL Call-to-action header text]** The words to display in the header above the Call-to-action button in the content modal. Default wording is, "Shop these products:".
  * **[!UICONTROL Call-to-action button text]** Customize the text on the Call-to-action button. Default text is, "Buy Now."
  * **[!UICONTROL Product display options]** Choose whether you want to display the **[!UICONTROL Photo]** and the **[!UICONTROL Product name]** with the Call-to-action button. 
  * **[!UICONTROL Product URL referral tracking]** Switch the toggle to on to track referrals from this App to the associated product page.
  * **[!UICONTROL Referral tracking key-value pairs]** Add parameters to further specify the referral tracking from your App content to the associated product page.

* **[!UICONTROL Product page filter]**

  * **[!UICONTROL Filter UGC by Product ID]**. Select this option to create one App for multiple product pages. Filter product-specific UGC to the App for each product page. You can select one or more folders to associate specific collections to the App.
  * **[!UICONTROL Select Product folders]**. Select the top-level product folders to use to filter UGC. Use `CTRL/Command + click` to select more than one folder. Livefyre uses the folder to determine which products in that folder to display in the App on various pages.
  * **[!UICONTROL Show related content]**. Toggle this to display content published to the App, but tagged with a different product ID. After the product-specific content for the App displays, Livefyre displays content for other products and content not associated with a product. Livefyre prioritizes the content with the same product ID first, then content published to the App with other product IDs, then content published to the App with no product IDs.
