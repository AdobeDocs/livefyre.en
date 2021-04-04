---
description: null
seo-description: null
seo-title: SSL Enforcement
solution: Experience Manager
title: SSL Enforcement
uuid: e64af8c2-3ab6-4034-b385-0e552d828c6e
exl-id: 033e15d9-84f6-42d5-8457-04263dcbd11c
---
# SSL Enforcement{#ssl-enforcement}

To ensure your data remains secure, we are deprecating HTTP in favor of HTTPS. Adobe Livefyre will disable all HTTP and insecure SSL/TLS ciphers completely by end of August 2018. This is an Adobe Standard designed to protect the privacy of you and your users.

## Who is affected? {#section_jf2_4yz_kcb}

This could impact Livefyre customers who have:

* Server-to-server calls from their CRM, CMS, WordPress, or other Client.
* Mobile Integrations (Android and iOS Apps)
* Custom applications or custom code

## What do I need to do? {#section_unv_dc5_kcb}

1. All Livefyre customers must communicate with all APIs via HTTPS for all traffic, including:

    * Server to Server Integrations (CRM, CMS, WordPress, etc.)
    * Mobile Integrations (Android and iOS Apps)
    * Custom Applications (Streamhub SDK or directly coded).

1. Server to Server and Mobile HTTP Clients must support TLS 1.2
1. Change hostnames from `{*}.<network>.fyre.co` to `<network>.{*}.fyre.co`. For example, the host name `example.network.fyre.co` changes to `network.`example.fyre.co``. For example:

    * `bootstrap.<network_name>.fyre.co` to `<network_name>.bootstrap.fyre.co`
    
    * `quill.<network_name>.fyre.co` to `<network_name>.quill.fyre.co`
    
    * `admin.<network_name>.fyre.co` to `<network_name>.admin.fyre.co`

## How do I know whether I made the changes? {#section_sqk_5d5_kcb}

You may already use HTTPS, but Livefyre recommends you double check, especially if you have:

* Server-to-server calls from your CMS or CRM.
* Custom code or use SDKs for custom apps in Javascript or Mobile.
* If your integration is more than one year old.
* If the technology in your stack is older than one year.

Even if you already use HTTPS, you must verify that your API clients support TLS 1.2.

## How can I verify that my API clients support TLS 1.2? {#section_nd1_j25_kcb}

A person who works on the development of your site can:

* Identify the client software.
* Identify the version.
* Read documentation to ensure the API client supports TLS 1.2.
* Turn on debug mode, if needed.

## Java Support for TLS 1.2 {#section_lwn_rwk_ycb}

Oracle and OpenJDK JVMs for Java 8 and later are configured to use TLS 1.2, by default, for all SSL connections. You do not need to take any additional action if you use Java 8 or later.

Users of Java 7 or earlier should consult public documentation on how to enable TLS 1.2.

## Why do I need to change my host names? {#section_d5q_p25_kcb}

Livefyre does not have SSL certificates on `{*}.<network>.fyre.co` domains. Simply changing the URL to HTTPS breaks the application.

## Do I have to upgrade to the latest version of Livefyre SDKs? {#section_dw5_s25_kcb}

No. You can patch the code instead. To patch the code, you modify some static strings and rebuild the code. If your HTTP client is out of date, you'll need to upgrade that as well or use a different one.

## How long will this take? {#section_lgd_v25_kcb}

The length of time this takes depends on your setup. If you have a simple implementation, it should take little time to confirm. If you have many customizations, you will need to test and deploy updated code to your servers or new Apps to App Stores. For best results, we recommend you do an initial audit of the work so you can plan for any longer-term work.

## What is the timeline for completing this work? {#section_kgk_w25_kcb}

Livefyre will disable port 80 (HTTP) to our services by the end of August 2018 and support only connections to 443 (HTTPS). Browsers and other clients, that attempt to use HTTP, will fail.

## When do I need to finish this work? {#section_rvb_x25_kcb}

All customers must use HTTPS by the end of July 2018. If you cannot meet this deadline, contact our team at prioritysupport@livefyre.com.
