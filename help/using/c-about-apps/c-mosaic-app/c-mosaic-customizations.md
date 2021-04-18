---
description: Change the size, width, and interaction options of the Mosaic app.
title: Mosaic Customizations
exl-id: 0223a64c-ec33-4e01-85d7-11845c9b8476
---
# Mosaic Customizations{#mosaic-customizations}

Change the size, width, and interaction options of the Mosaic app.

 All Apps use **[!UICONTROL Style]** and **[!UICONTROL Config]** options in the **[!UICONTROL App Designer]**. See Customizing Apps for details on the standard **[!UICONTROL Style]** and **[!UICONTROL Config]** options for all Apps in the **[!UICONTROL App Designer.]**

You can customize Mosaic using the following additional options in the App Designer:

* **[!UICONTROL Content interaction]**. Sets the style with which new content will be loaded onto the page:

    * **[!UICONTROL Hover Fade]** to fade to the other side of a card when a site visitor hovers their mouse over the content.
    * **[!UICONTROL Hover Flip]** to flip to the other side of a card when a site visitor hovers their mouse over the content.
    * **[!UICONTROL Click]** to display the other side of a card when a site visitor clicks their mouse on the content.

* **[!UICONTROL Number of Tiles to Load]**. The number of tiles to load in a Mosaic. This can affect the output display. Mosaic will not display in a grid unless you choose the correct number of tiles to correspond to the container width. You may need to adjust these for the grid to display correctly. 
* **[!UICONTROL Hide social branding when rights granted]** Switch this on to remove the logo for the originating social media network (Twitter or Instagram) when rights are granted for a piece of content. 

* **[!UICONTROL Call-to-action button]** You can use the Call-to-action button with a product catalog to direct users to a product or to your site for further action.

    * **[!UICONTROL Call-to-action button]** Switch the toggle to on to display the Call-to-action button.
    
    * **[!UICONTROL Require rights to display products]** Switch the toggle to on to require that the content owner has granted rights for the content before a Call-to-action button appears for the content.

      >[!NOTE]
      >
      >The content displays even if rights are not granted for the content, but the Call-to-action button will not display with the content unless rights for the content are granted.

    * **[!UICONTROL Show call-to-action in tile]**. Choose whether to display the call-to-action button on a Filmstrip tile instead of displaying the call-to-action button only when the site visitor clicks on a card and opens the content in a larger window.
    * **[!UICONTROL Call-to-action indication text]** The text to display to prompt the user to click on the card to open the Call-to-action modal.
    
    * **[!UICONTROL Call-to-action header text]** The words to display in the header above the Call-to-action button in the content modal. Default wording is, "Shop these products:".
    
    * **[!UICONTROL Call-to-action button text]** Customize the text on the Call-to-action button. Default text is, "Buy Now."
    
    * **[!UICONTROL Product display options]** Choose whether you want to display the **[!UICONTROL Photo]** and the **[!UICONTROL Product name]** with the Call-to-action button. 
    
    * **[!UICONTROL Product URL referral tracking]** Switch the toggle to on to track referrals from this App to the associated product page. 
    
    * **[!UICONTROL Referral tracking key-value pairs]** Add parameters to further specify the referral tracking from your App content to the associated product page.

* **[!UICONTROL Product page filter]**.

    * **[!UICONTROL Filter UGC by Product ID]**. Select this option to create one App for multiple product pages. Filter product-specific UGC to the App for each product page. You can select one or more folders to associate specific collections to the App.
    * **[!UICONTROL Select Product folders]**. Select the top-level product folders to use to filter UGC. Use CTRL/Command + click to select more than one folder. Livefyre uses the folder to determine which products in that folder to display in the App on various pages.
    * **[!UICONTROL Show related content]**. Toggle this to display content published to the App, but tagged with a different product ID. After the product-specific content for the App displays, Livefyre displays content for other products and content not associated with a product. Livefyre prioritizes the content with the same product ID first, then content published to the App with other product IDs, then content published to the App with no product IDs.

See [Mosaic Options](/help/implementation/c-getting-started/c-implementation-process/c-using-livefyre.js-to-create-customize-and-use-apps-on-your-site.md) for more on how to customize a Mosaic using Livefyre.js.
