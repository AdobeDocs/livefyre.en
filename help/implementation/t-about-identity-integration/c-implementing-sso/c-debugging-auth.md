---
description: You can log a user in through the console during integration and testing to debug authorization.
title: Debugging Auth Delegate
exl-id: fa1c17fa-5aba-4f4c-9217-5823af30af61
---
# Debugging Auth Delegate{#debugging-auth-delegate}

You can log a user in through the console during integration and testing to debug authorization.

Log a user in through the console using the following `auth.authenticate` (token) and pass a Livefyre user token to authenticate users on the page.

You may also modify the example shown above, and add the following snippet in-line in your JavaScript to quickly log a user into Livefyre (requires a reference to auth).

```
window.addEventListener('userAuthenticated', function(data) { 
 Livefyre.require(['auth'], function (auth) { 
  auth.authenticate({livefyre: data.token}); 
 }); 
});
```
