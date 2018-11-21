---
description: Remove standard Livefyre App components from your App.
seo-description: Remove standard Livefyre App components from your App.
seo-title: Hide App Elements
solution: Experience Manager
title: Hide App Elements
uuid: 34240022-071b-4f9c-b757-96bd9b4f961e
index: y
internal: n
snippet: y
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

