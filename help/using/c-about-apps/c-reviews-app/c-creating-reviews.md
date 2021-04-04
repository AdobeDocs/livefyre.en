---
description: Reviews offers a broad range of customizations, allowing you to create a Review App which matches your needs and branding.
seo-description: Reviews offers a broad range of customizations, allowing you to create a Review App which matches your needs and branding.
seo-title: Creating a Reviews App
solution: Experience Manager
title: Creating a Reviews App
uuid: 6caeafe7-c04e-484e-b02f-98dc6d9b3184
exl-id: 14f074d2-922c-4997-8d7d-f2c92f069e07
---
# Creating a Reviews App{#creating-a-reviews-app}

Reviews offers a broad range of customizations, allowing you to create a Review App which matches your needs and branding.

Use the Reviews App by custom-embedding it on your site as a JS application. You cannot create a Reviews App in Livefyre Studio. To create a Reviews App on your site, see [Reviews Integration](/help/implementation/c-app-integrations/c-reviews-integration.md).


## Ratings {#section_hs5_c4h_21b}

Ratings are the numerical value your users assign to the Review. Every Review must include a Rating, which is shown as a 5 star system by default. (While ratings are displayed as 0.5 - 5 in the App, Livefyre stores a ratio of X/100 in the backend, such that 1 star is 20/100, and 2 stars is 40/100. This ratio is displayed when viewing the reviews within Studio.)

The Rating scale of 0.5 through 5 can be configured up to a rating of 100, with half ratings also available.

For more information, see the maxRating field for the Reviews convConfig object.

## Rating Icon Styling {#section_cqn_c4h_21b}

Rating icons may be customized to fit your branding and style.

For more information, please see **[!UICONTROL Configure Star Ratings]** under Reviews Customization.

## Rating Dimensions {#section_cnx_snh_21b}

Rating dimensions are the categories about which your reviewers are rating your product or service. Examples of rating dimensions are “performance,” “design,” “cost,” “overall,” or any other category you choose.

The default is to display one “overall” rating dimension, however you may define and implement multiple rating dimensions, as displayed in the example below.

For more information, see the ratingDimensions field under Review Collection Metadata.

## Review Text Fields {#section_xcm_4nh_21b}

You may also include additional text fields on the product or experience being reviewed. (For example, text fields might include Pros and Cons, or Don’t Miss.) The number, title and default text for the field are customizable. Users will be required to complete all text fields, as well as the review title, body and rating, in order to publish their review. It is not possible to include optional text fields.

For more information, see the ratingDimensions field for the Review Collection Metadata.

## Review Summary {#section_ysz_lnh_21b}

By default, a summary section is displayed at the top of the Reviews App. This section includes a visualization of the Average User Rating and the Rating Breakdown for the Reviews Collection, displaying whole numbers only. This section is read-only and can be hidden if desired.

For more information, see the ratingSummaryEnabled field for the Reviews convConfig object.

## Spam and Profanity Filter {#section_hcm_jnh_21b}

The text of a Review’s Title and Body is passed through our Spam Filter and Profanity Filter as soon as the Review is posted.

## Text Customization {#section_tjf_hnh_21b}

Text strings, including tooltips and labels, may be customized for language or to fit your brand.

## Replying to a Review {#section_yng_fnh_21b}

Users may reply to their own or other’s Review in each Reviews Collection. Only users who are logged in can post a reply to a review.

The option for users to reply to a Review is enabled in Studio. Owners may toggle this setting for the Network, Site or Collection level. Moderators may enable this setting only for their Collections.

## SocialSync and Curate {#section_llh_2nh_21b}

Because Reviews is designed to add a numerical value for each piece of submitted content, SocialSync and Curate are not supported with the Reviews.

## Reviews APIs {#section_xrh_wmh_21b}

Reviews APIs are available to allow you to display average user rating and rating breakdown information and user reviews activity on other sections across your site.

[Ratings and Reviews](https://api.livefyre.com/docs/apis/by-category/ratings-and-reviews)

* **[!UICONTROL Bootstrap API Endpoint]** The Bootstrap API Endpoint allows your review to be read by search engines like Google so that the content and keywords can improve your search engine optimization.

* **[!UICONTROL Average User Ratings]** The Average User Ratings API retrieves the average user rating for one or more Reviews Collections, allowing you to create a visualization of this information on an index page or add to a search index page.

* **[!UICONTROL Ratings Breakdown]** The Ratings Breakdown API retrieves a breakdown of all ratings for a specific Reviews Collection and allows you to create a visualization that displays the number of reviews that are associated with each star rating.

* **[!UICONTROL User Reviews]** The User Reviews API retrieves the most recent reviews for a specific user. This activity can be used to display a user’s reviews on their public profile page.
