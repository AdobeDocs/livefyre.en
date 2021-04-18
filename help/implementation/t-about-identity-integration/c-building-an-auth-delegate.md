---
description: The AuthDelegate object implements your desired behavior for how to perform authentication actions and events so you can customize integration with your site’s existing authentication system.
title: AuthDelegate Object
exl-id: 7c669138-627e-476e-a177-c71346f730df
---
# AuthDelegate Object{#authdelegate-object}

The AuthDelegate object implements your desired behavior for how to perform authentication actions and events so you can customize integration with your site’s existing authentication system.

## Building an Auth Delegate {#section_wmn_tv2_gz}

The auth package must be provided with an auth delegate before it can perform an action. An auth delegate is any JavaScript object that implements one of the methods in this topic.

## .login(finishLogin) {#section_mpk_lv2_gz}

Log in a valid user and invoke the finishLogin function with either an Error object if there was an error, or the user’s Livefyre credentials. Common implementations of this method redirect the user to a login page or open a new window or modal.

This example automatically notifies auth of a Livefyre user with the authentication token, token:

```
authDelegate.login = function (finishLogin) { 
 finishLogin(null, { 
   livefyre: 'token' 
 }); 
};
```

The simplest login delegate might ask the end-user for their Livefyre Authentication token.

```
authDelegate.login = function contrivedLogin(finishLogin) { 
  var lfToken = prompt("Please type your Livefyre Token");  
  if (lfToken.length === 0) { 
   return finishLogin(new Error("User failed to type their lftoken")); 
  }  
 finishLogin(null, { 
   livefyre: lfToken 
 }); 
};
```

## .logout(finishLogout) {#section_uqz_2v2_gz}

Log out a user and invoke the finishLogout function with either an Error object if there was an error, or null to notify auth that the logout was successful.

For example:

```
authDelegate.logout = function (finishLogout) { 
 clearUserSession(); //logic to clear a user session  
 finishLogout(null); 
}
```

## .viewProfile(user) {#section_kkv_dv2_gz}

Take action to view a user’s profile.

```
authDelegate.viewProfile = function (user) { 
 window.open(user.get('profileUrl')); 
}
```

## .editProfile(user) {#section_bkx_pq2_gz}

Take action to edit a user’s profile.

```
authDelegate.editProfile = function (user) { 
 window.open(user.get('profileUrl') + '/edit/'); 
}
```

By implementing all of the methods listed above, auth can be configured with a custom auth delegate. Once a delegate has been constructed, it can be provided to auth using the delegate method.

```
var authDelegate = { 
 login: function(cb) { 
  ... 
  cb(null); 
 }, 
 ... 
} 
  
auth.delegate(authDelegate);
```
