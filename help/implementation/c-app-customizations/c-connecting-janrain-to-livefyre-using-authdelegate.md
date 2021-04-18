---
description: Livefyre.require provides a plugin that enables auth to listen to the Janrain Backplane bus.
title: Connecting Janrain to Livefyre using AuthDelegate
exl-id: d0fe0e88-5827-478b-b2ef-03f06fb3902c
---
# Connecting Janrain to Livefyre using AuthDelegate{#connecting-janrain-to-livefyre-using-authdelegate}

Livefyre.require provides a plugin that enables auth to listen to the Janrain Backplane bus.

When an identity/login message is broadcast on the Backplane channel, auth.authenticate() will be called for you with the user’s Livefyre Authentication token. You must still implement an AuthDelegate.

```
Livefyre.require(['auth', 'backplane-auth-plugin#0'], function(auth, backplanePluginFactory) { 
   auth.plugin(backplanePluginFactory('network.fyre.co')); 
   auth.delegate({ 
      login: function (finishLogin) { 
         loginWithCapture(finishLogin); 
      } 
   }); 
});
```

>[!NOTE]
>
>The window.Backplane object must be defined on your page before calling auth.plugin with the Livefyre Backplane plugin. To make sure the Backplane object is available, call the Livefyre instantiation code from an onReady callback. Consult your Janrain contact to determine when other applications may use the Backplane object.

The following are some examples of how an auth delegate may look for a Janrain Capture integration.

>[!NOTE]
>
>Your auth delegate will vary depending upon your Janrain instance.

<!--Hannah: Mystery stray bullet found here. Please check against source. -Bob -->

* The callback passed to your auth delegate’s login method
* The reference to your Janrain capture variable.
* : A reference to your Backplane object.

```
/** 
* Login function 
* In this case, opens a login modal and triggers Backplane to start listening 
* for login messages 
*/ 
authDelegate.login = function(finishLogin) { 
   var successCallback = function() { 
      // These need to be replaced with the actions that correspond to successful login  
      // and when the Janrain modal is closed. 
      janrain.events.onCaptureLoginSuccess.removeHandler(successCallback); 
      janrain.events.onModalClose.removeHandler(failureCallback); 
      finishLogin(); 
   }; 
  
   var failureCallback = function(e) { 
      janrain.events.onModalClose.removeHandler(failureCallback); 
      janrain.events.onCaptureLoginSuccess.removeHandler(successCallback); 
      finishLogin(e || new Error("Error logging in with Janrain Capture")); 
   }; 
  
   // Open the modal to log a user in 
   janrain.capture.ui.renderScreen('signIn'); 
   // Send a backplane message 
   window.Backplane.expectMessages('identity/login'); 
   // Add handlers to specific janrain events 
   janrain.events.onCaptureLoginSuccess.addHandler(successCallback); 
   janrain.events.onModalClose.addHandler(failureCallback); 
};
```

Logout

* **finishLogout:** The callback passed to your auth delegate’s login method.

* **window.Backplane:** A reference to your Backplane object.

```
/** 
* Logout function 
* In this case, invalidates the session and removes the cookie. 
* Also reloads the page to change state. In order to do this without a reload, 
* it would be necessary to also update the UI. 
*/ 
authDelegate.logout = function(finishLogout) { 
   Backplane.resetCookieChannel(); 
   janrain.capture.ui.endCaptureSession(); 
   finishLogout(); 
}; 

```

Edit Profile

This can link to whatever part of the site you would like users to visit to view their own profile page. This example merely prints out the author object passed in.

```
/** 
* Edit profile function 
* @param user - User who would like to edit their profile 
*/ 
authDelegate.editProfile = function(user) { 
   console.log(user); 
}; 

```

View Profile

Like Edit Profile, this should link to a user’s page that is different from the currently logged in user. This can be implemented however you see fit. This example simply logs the author parameter to the console.

```
/** 
* View profile function 
* @param user - User or userId whose profile should be displayed 
*/ 
authDelegate.viewProfile = function(user) { 
   console.log(author); 
};
```
