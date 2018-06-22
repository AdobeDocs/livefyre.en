---
description: What to expect in implementing Livefyre Studio.
seo-description: What to expect in implementing Livefyre Studio.
seo-title: Implementation Process
title: Implementation Process
---

# Implementation Process

<!-- c_implementation_process.dita -->
The length of time to implement Livefyre depends on your implementation and scope of work.

## Overview of Livefyre Network Architecture {#section_dgj_l32_rbb}

Livefyre uses the following terms in discussing network architecture:

* Network. The highest-level domain on which you plan to use Livefyre.
* Sites. A subdomain or site section that is part of the network.
* Apps. A rendering of content on your site. Content is displayed in Apps visually, using Visualization Apps (Mosaic, Carousel, Feature Card, etc.) or in text format, using Conversation Apps (Comments, Reviews, Chat, etc.). You can put one or more Apps on your sites.
* Streams. Streams are filters that search social media and other sites to gather content automatically for moderation or direct publishing in an App.
* Content (for example, UGC, comments). What displays in the Apps. Content can be visual (for example, a photo or video), audio-only, or text.
The following diagram shows the relationship between Network, Sites, Apps, and Content.

![](images/network_site_architecture.png)
You have your own Livefyre instance which is your central dashboard for moderating content, managing users, and more. Contact your CSM for access to your Livefyre instance.

## Integration Steps {#section_s2j_d2x_tz}

There are three main steps to integrating Livefyre:

  *
  App Integration
  
  When you implement Livefyre, the style of implementation depends on your use case. For more on each implementation type, see [](c_app_integration_types.md#c_app_integration_types).
  
  
  *
  Authentication Integration
  
  You must integrate your existing user management system with Livefyre for conversation Apps and any other Apps that require end-user authentication on your site. If you do not currently use a user management tool, you can use Livefyre Identity. For more information about Livefyre Identity, what it is, and how to set it up, see [](c_livefyre_identity_comp.md#c_livefyre_identity)..
  
  
  *
  Customization
  
  Customization is optional, but most customers customize Apps to fit their brand.
  
  
