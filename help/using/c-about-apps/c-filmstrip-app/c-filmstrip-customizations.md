---
title: Filmstrip Customizations
description: Filmstrip Customizations
exl-id: 2765699f-7adc-4b17-acfb-ef594ff65e89
---
# Filmstrip Customizations{#filmstrip-customizations}

All Apps use **[!UICONTROL Style]** and **[!UICONTROL Config]** options in the **[!UICONTROL App Designer]**. See Customizing Apps for details on the standard **[!UICONTROL Style]** and **[!UICONTROL Config]** options for all Apps in the **[!UICONTROL App Designer.]**

You can customize Filmstrip using the following additional options in the App Designer:

* **[!UICONTROL Content fit]**. Choose **[!UICONTROL crop]** to crop the content to fill the card or **[!UICONTROL Aspect Ratio]** to display an entire image in the card, whether it fills up the entire card or not.
* **[!UICONTROL Tile Size]**. Enter the size of the tiles in pixels. 
* **[!UICONTROL Show Notifications]**. Choose whether to display a notification for new content as it streams into the Filmstrip App.
* **[!UICONTROL Require rights]**. Enable this option to display only content with a rights request status of "Granted."
* **[!UICONTROL Hide social branding when rights granted]** Switch this on to remove the logo for the originating social media network (Twitter or Instagram) when rights are granted for a piece of content. 
* **[!UICONTROL Call-to-action button]** You can use the call-to-action button with a product catalog to direct users to a product or to your site for further action.

  * **[!UICONTROL Call-to-action button]** Switch the toggle to on to display the call-to-action button.
  * **[!UICONTROL Require rights to display products]** Switch the toggle to on to require that the content owner has granted rights for the content before a call-to-action button appears for the content.

    >[!NOTE]
    >
    >The content displays even if rights are not granted for the content, but the call-to-action button will not display with the content unless rights for the content are granted.

  * **[!UICONTROL Show call-to-action in tile]**. Choose whether to display the call-to-action button on a Filmstrip tile instead of displaying the call-to-action button only when the site visitor clicks on a card and opens the content in a larger window.
  * **[!UICONTROL Call-to-action indication text]** The text to display to prompt the user to click on the card to open the call-to-action modal.
  * **[!UICONTROL Call-to-action header text]** The words to display in the header above the call-to-action button in the content modal. Default text is, "Shop these products:".
  * **[!UICONTROL Call-to-action button text]** The words to display in the call-to-action button in the content modal. Default text is, "Buy Now:".
  * **[!UICONTROL Product display options]** Choose whether you want to display the **[!UICONTROL Photo]** and the **[!UICONTROL Product name]** with the call-to-action button.

    >[!NOTE]
    >
    >Both the Photo and Product name buttons highlight blue when they are enabled.

  * **[!UICONTROL Product URL referral tracking]** Switch the toggle to on to track referrals from this App to the associated product page. 
  * **[!UICONTROL Referral tracking key-value pairs]** Add parameters to further specify the referral tracking from your App content to the associated product page.

* **[!UICONTROL Embed App in multiple pages]**.

  * **[!UICONTROL Filter UGC by Product ID]**. Select this option to create one App for multiple product pages. Filter product-specific UGC to the App for each product page. You can select one or more folders to associate specific collections to the App.
  * **[!UICONTROL Select product folders]**. Select the top-level product folders to use to filter UGC. Use CTRL/Command + click to select more than one folder. Livefyre uses the folder to determine which products in that folder to display in the App on various pages.
  * **[!UICONTROL Show related content]**. Toggle this to display content published to the App, but tagged with a different product ID. After the product-specific content for the App displays, Livefyre displays content for other products and content not associated with a product. Livefyre prioritizes the content with the same product ID first, then content published to the App with other product IDs, then content published to the App with no product IDs.

See [Filmstrip Options](/help/implementation/c-getting-started/c-implementation-process/c-using-livefyre.js-to-create-customize-and-use-apps-on-your-site.md) for more on how to customize a Filmstrip using Livefyre.js.
