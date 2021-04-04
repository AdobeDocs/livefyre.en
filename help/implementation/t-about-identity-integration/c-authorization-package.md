---
description: Install the Authentication Package to enable user authentication so users can interact with your apps.
seo-description: Install the Authentication Package to enable user authentication so users can interact with your apps.
seo-title: Authentication Package
solution: Experience Manager
title: Authentication Package
uuid: 4eec30cf-66b6-408d-985d-3e23b8b70d01
exl-id: 639032ee-ed7d-4cb0-83ba-f11d3dc607b6
---
# Authentication Package{#authentication-package}

Install the Authentication Package to enable user authentication so users can interact with your apps.

Livefyre Apps use the global auth package to associate users with App actions. The auth package is available through `Livefyre.require`.

To enable authentication on your page, first add `Livefyre.js` to the `<head>` element of your webpage or website template.

```
<script src="//cdn.livefyre.com/Livefyre.js"></script>
```

Using Livefyre.require to enable auth is similar to using require to call other packages. The integration code to require auth looks like this:

```
Livefyre.require(['auth'], function (auth) {  
// Perform action... 
});
```

## Methods {#section_ojx_1lz_fz}

Once included as above using `Livefyre.require`, the Auth module exposes the following methods that you can call to notify other Apps on the page about authentication-related events.

|Method|Description|
|--- |--- |
|`.login(callback)`|Trigger the login flow as implemented by the registered AuthDelegate. Usually only auth-enabled Apps will call this, and not the host page itself.|
|`.logout(callback)`|Notify auth that the end-user has logged out by some external means, and that all relying Apps should clear their authentication state until the next login. This will clear the internal session maintained by Auth.|
|`.authenticate(credentials)`|Notify Auth that a user has authenticated by some external means, and a Livefyre Authentication Token has been procured for the end-user. Use this if you set a cookie with the Livefyre token, or have a token for the user and want to explicitly log the user in. For example: <br>`auth.authenticate({&nbsp;livefyre:&nbsp;`<br>`'<insert&nbsp;lftoken&nbsp;string&nbsp;for&nbsp;newly&nbsp;logged-in&nbsp;user>'&nbsp;});`|
|`.delegate(authDelegate)`|Delegate the implementation details of authentication (for example, your custom authentication flow) to an object that you define. This must be called by the host page to enable interactive features of Livefyre Apps.|
