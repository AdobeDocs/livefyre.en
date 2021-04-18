---
description: You can change the warning text that displays on video masks using .
title: userPrivacyMaskDelegate

---

# userPrivacyMaskDelegate{#userprivacymaskdelegate}

You can change the warning text that displays on video masks using .

This text exists to comply with the GDPR regulation. If a source does not support a proxy, then Livefyre displays this text and a mask on the content unless a user clicks on the video and approves the potential tracking from that source.

If you do not use `userPrivacyMaskDelegate`, the following default text displays:

Add `userPrivacyMaskDelegate` after `userPrivacyOptOut`. You can add all the Livefyre privacy flags all at once as part of one Livefyre object.

Here is an example of how to use `userPrivacyMaskDelegate`:

```
userPrivacyMaskDelegate: function () { 
    var container = document.createElement('div'); 
    var firstParagraph = document.createElement('p'); 
    firstParagraph.innerHTML = 'Text of first paragraph'; 
    var secondParagraph = document.createElement('p'); 
    secondParagraph.innerHTML = 'Text of second paragraph'; 
    container.appendChild(firstParagraph); 
    container.appendChild(secondParagraph); 
    return container; 
}
```
