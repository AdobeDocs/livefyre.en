---
description: Remove standard Livefyre App components from your App.
title: Hide App Elements
exl-id: f8bbed2c-d009-41b8-927d-8d6ac4a63571
---
# Hide App Elements{#hide-app-elements}

Remove standard Livefyre App components from your App.

Use CSS to hide default Livefyre App elements from your page, allowing you to customize the user experience to fit your needs.

To hide elements from the App, simply set display to none.

Examples:

```
/* Hide the 'reply' button */ 
.fyre-comment-reply { 
    display: none !important; 
} 
  
/* Hide all user avatars */ 
.fyre-comment-user .fyre-mention-item-avatar .fyre-listener-avatars .fyre-avatar fyre-user-avatar-25 { 
    display: none !important; 
} 
.fyre-comment-head .fyre-comment-body .fyre-comment-footer .fyre-comment-divider { 
    margin-left: 0; 
} 
  
/* Hide 'Edit Profile' link */ 
.fyre-edit-profile-link { 
    display: none !important; 
} 
  
/* Hide 'Logout' link */ 
.fyre-logout-link { 
    display: none; 
} 
  
/* Hide 'Comment Notifier' */ 
.fyre-notifier-message { 
    display:none; 
}
```
