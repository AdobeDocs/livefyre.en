---
title: Emails for Livefyre Identity
description: Emails for Livefyre Identity
exl-id: c8127eef-8fb8-4703-ba34-ef12453f1754
---
# Emails for Livefyre Identity{#emails-for-livefyre-identity}

Livefyre Identity sends the following emails:

* [Password Reset Email](#c_emails_for_livefyre_identity/section_nd1_whs_p1b) 
* [Verification Email](#c_emails_for_livefyre_identity/section_ak5_xhs_p1b)
  * [Send Email Verification for Users](#c_emails_for_livefyre_identity/section_vyv_yhs_p1b)

* [Welcome Email](#c_emails_for_livefyre_identity/section_z2v_zhs_p1b)
  * [Send Welcome Email to Users](#c_emails_for_livefyre_identity/section_kjp_c3s_p1b)

You can customize the look and feel of all Livefyre Identity emails in **[!UICONTROL Integration Settings > Email Notifications.]**

## Password Reset Email {#section_nd1_whs_p1b}

Livefyre automatically sends a password reset email when a user tries to reset their password.

The password reset email looks like this:

**Subject:** Reset Password

**Body:**

Hey there *&lt;username&gt;*,

There was a request to change the password of your profile on *&lt;network name&gt;*.

If you requested this, please click the following link to choose a new password: *&lt;password reset URL&gt;*.

*&lt;Username&gt;*, *&lt;network name&gt;*, and *&lt;password reset URL&gt;* are all dynamically generated based on the site visitor and your network.

## Verification Email {#section_ak5_xhs_p1b}

You can send an email verifying the email address of a user. To send verification emails, you must turn on the option in **Integration Settings > Livefyre Identity**.

The verification email looks like this:

**Subject:** Email Verification

**Body:**

Hello *&lt;username&gt;*,

Please click on the following link (or paste in your browser) to verify your account: *&lt;verification URL&gt;*.

This link will expire in 24 hours.

Thanks,

The *&lt;customer name&gt;* Team

*&lt;Username&gt;*, *&lt;network name&gt;*, and *&lt;verification URL&gt;* are all dynamically generated based on the site visitor and your network.

## Send an Email Verification to Users {#section_vyv_yhs_p1b}

You can send an email to a user to verify the email address they use to sign up for an account. To send a verification email:

1. In Studio, click on the gear icon to modify network settings.
1. Click **Integration Settings > Livefyre Identity.**

1. Navigate to **Login Types**.
1. Click **Require Email Verification** to send an email to users that verifies the email address they use to sign up for an account.
1. Navigate to **Network Email** to configure the **Logo for Email**, the email address to use as the from address (**Email From**), and the display name to use for the from email address (**Email Display Name**).

## Welcome Email {#section_z2v_zhs_p1b}

You can send a welcome email to users. To send welcome emails, you must turn on the option in **Integration Settings** > **Livefyre Identity**.

The welcome email looks like this:

**Subject:** Welcome to *&lt;customer name&gt;*

**Body:**

Hello *&lt;username&gt;*,

An account was created for you on *&lt;customer name&gt;*.

This account was created on *&lt;referral URL&gt;* from IP address *&lt;IP Address&gt;*.

If you did this, you can safely disregard this email.

If you didn’t do this, please contact `support@livefyre.com`

Thanks

The *&quot;customer name&quot;* Team

*&quot;Username&quot;, &quot;customer name&quot;, &quot;referral URL&quot;,* and &quot;IP Address&quot; are all dynamically generated based on the site visitor and your network.

## Send a Welcome Email to a User {#section_kjp_c3s_p1b}

You can send a welcome email to a user after they sign up for an account. Studio sends this email after it sends a verification email, if you set up a verification email. To send a welcome email:

1. In Studio, click on the gear icon to modify network settings.
1. Click **[!UICONTROL Integration Settings > Livefyre Identity]**

1. Navigate to **[!UICONTROL Email Settings]**.

1. Click **[!UICONTROL Send Welcome Emails To New Users]** to enable sending emails.
1. Navigate to **[!UICONTROL Network Email]** to configure the *Logo for Email*, the email address to use as the from address (**Email From**), and the display name to use for the from email address (**Email Display Name**).
