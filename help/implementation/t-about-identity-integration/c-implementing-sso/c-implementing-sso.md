---
description: To authenticate a user with Livefyre through a flow not triggered by a Livefyre App, Livefyre recommends that you implement the forEachAuthentication method on your AuthDelegate object.
title: Implementing SSO
exl-id: 9af75b8a-9d2a-446e-8cce-2de8645038f2
---
# Implementing SSO{#implementing-sso}

To authenticate a user with Livefyre through a flow not triggered by a Livefyre App, Livefyre recommends that you implement the forEachAuthentication method on your AuthDelegate object.

This will be invoked when the `authDelegate` is passed to `auth.delegate`, and will be passed an authenticate function that can be passed multiple times. This method provides an inversion of control for authentication events so that your `AuthDelegateobject` can be self-contained without requiring a global reference to auth.

```
authDelegate.forEachAuthentication = function (authenticate) { 
 window.addEventListener('userAuthenticated', function(data) { 
  authenticate({livefyre: data.token}); 
 }); 
}
```

Livefyre relies on user tokens to coordinate authentication. As a result, this token must be returned by your identity service to authenticate a user with Livefyre. To learn how to create a Livefyre user token, please see Building a User Authentication Token.

>[!NOTE]
>
>After a successful login, auth will create a session for the user, and will try to load a user’s session upon page refresh and reload. `auth.logout()` will clear this session. This means that it is not necessary to manage a user’s session independently of authorization.
