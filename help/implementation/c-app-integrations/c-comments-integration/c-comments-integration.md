---
description: Enable live commenting on your page.
seo-description: Enable live commenting on your page.
seo-title: Comments
solution: Experience Manager
title: Comments
uuid: decad9b0-2074-4748-bd77-914008817bfa
exl-id: d62b3dc1-3c5e-45f6-9b21-ea1edcda9812
---
# Comments{#comments}

Enable live commenting on your page. Comments allows you to replace your default commenting system with real-time conversations on your page.

## Integration {#concept_4093E8BAA96A464BA74D263DA031C0B0}

Embedding the Comments App follows the process for embedding a Core App described in Getting Started > Embedding an App.

### Example

```
<html> 
  <head> 
    <script src="//cdn.livefyre.com/Livefyre.js"> 
    </script> 
  </head> 
<body> 
    <script type="text/javascript"> 
    var networkConfig = { 
      network: 'domainName' 
    }; 
    var convConfig = { 
      siteId: 'siteId', 
      articleId: 'articleId', 
      el: 'livefyre', 
      collectionMeta: 'collectionMeta', 
      checksum: 'checksum' 
    }; 
    
    Livefyre.require(['fyre.conv#3', 'auth'], function(Conv, auth) { 
        new Conv(networkConfig, [convConfig], function(commentsWidget) {}); 
        auth.delegate({ 
            login: function (callback) { 
                callback(null,{livefyre:'<userauthtoken>'}); 
            }, 
        }); 
    }); 
  
    </script> 
    <div id="livefyre"> 
    </div> 
   </body> 
</html>
```

As noted in the Building CollectionMeta section, CollectionMeta is an encoded JSON object. In the above example, the JSON object takes the following format before it's JWT encoded:

```
{ 
"url": "articleUrl",  
"articleId": "articleId",  
"type": "livecomments",  
"title": "articleTitle" 
}
```

## NetworkConfig Object {#c-networkconfig-object}

The `NetworkConfig` object is a JSON object that customizes the authentication system for network users.
The `NetworkConfig` object is a JSON object containing the following parameters:

|  Parameter  | Type  | Description  |
|---|---|---|
|  **authDelegate** | *required*  object | Used to customize the authentication system for custom network users.  |
|  **network** | String *required*  | A Livefyre-provided network name. For example: *yourname.fyre.co.* |
|  **attachmentDelegate** |  *optional* object | Used to specify the types of media attachments visible in the App stream. For more information, see [Restricting Media](/help/implementation/c-app-customizations/c-restrict-media.md#c_restrict_media).  |
|  **strings** |  *optional* object | Used to customize text strings of the HTML elements in any of the Livefyre Core Apps. For more information, see [String Customizations](/help/using/c-settings-other/c-translation-sets/c-localize-strings.md).  |

## ConvConfig Object {#c-convconfig-object}

The `convConfig` object is a JSON object used to specify the content that the Livefyre App renders on the page.

>[!NOTE]
>
>The `convConfig` object parameters listed here do not apply for the Reviews app. For integration information about the Reviews app using the `convConfig` object, see Reviews Integration.

The `ConvConfig` object contains the following required parameters: 

|Parameter|Type|Description|
|--- |--- |--- |
|**articleId**| *required* string |Uniquely identifies a Collection within your Site. Usually, this corresponds to a database primary key or Post ID within your CMS. For example: “post-42”. 255 character limit.  Note:  If you use the article URL as your articleId, make certain the string is MD5 or SHA-1 encoded.|
|**authPageReload**| *optional*  boolean|Applies to Comments App: Allows you to control whether a user’s comment is stored locally during the auth process. If true, if a user enters a comment, and then logs into the App, the comment will be stored locally, and will be re-entered in the content field after login and page refresh. If false, entered content will be wiped during the login process, and must be retyped.|
|**collectionMeta**|*required* string |JWT-encoded metadata about the Collection. See  [CollectionMeta](#c_collectionmeta_object) Object  for more information.|
|**el**| *required* string|The ID of a DOM element to which the content stream will render.|
|**siteId**| *required* string|The Livefyre-provided ID for the website or application to which the Collection belongs. For example: “303617”.|

>[!NOTE]
>
>The `app` parameter is not required for a Comments App implementation.

The `ConvConfig` object may also contain the following optional parameters: 

|Parameter|Type|Description|
|--- |--- |--- |
|**actionButtons**| *optional* array|An array of custom action buttons to add to a piece of content next to the  Share  and  Flag  buttons. For more information, see Adding Custom Buttons.|
|**animations**|*optional* boolean |Defines whether animations will run within the Livefyre App. Set to false to disable animations. Defaults to true.|
|**anonymousFlaggingEnabled**| *optional* boolean|Defines whether guest users have the option to flag content. Default is true.|
|**browserType**|*optional* string |Defines the device for which display content should be generated. This will cause the CSS, and some functionality, to change to fit the input device type. Options are desktop, mobile, or tablet. (If left blank, will default to the Google Agent determination for the display format.)|
|**checksum**| *recommended* string|Identifies the current state of the CollectionMeta. Changing this value will cause Livefyre to update the data on the server with the new values in CollectionMeta.|
|**datetimeFormat**|*optional*  string  object function|Specifies the datetime format of streamed content. For more information, see Customizing Date and Time Stamps.|
|**disableAvatars**|*optional* boolean |Prevents avatars from being rendered in the App stream, and thus reduces the number of items loaded into the browser. Default is false.|
|**disableIE8Shim**|*optional* boolean |Disables the default shiv used by Livefyre to polyfill Internet Explorer 8 so that HTML5 elements are supported. Livefyre uses the following project:  [https://github.com/aFarkas/html5shiv](https://github.com/aFarkas/html5shiv) . Default is false.  Note:  If this value is false, polyfill of some sort must be used before Livefyre Chat is invoked for Internet Explorer 8 support.|
|**disableThirdPartyAnalytics**| *optional* boolean|Disables third party analytics systems (Quantserve and Google Analytics) that Livefyre may use for internal measurements. Default is false.|
|**editorCss**|*optional* object |Used to customize the comment editor styling. You may style the editor field background color as well as the font color, size, and family of the text that appears inside the editor.  For example: `{background: ‘#ccc’, color: ‘red’, font: ’30px “Helvetica Neue”, Helvetica, Arial, Geneva, sans-serif’}`|
|**initialNumVisible**| *optional* integer|Allows you to set the default number of comments visible in your App upon load. This may be an integer from 1 to 50.|
|**initialNumVisibleLegacy**| *optional* integer|Allows you to set the default number of legacy content items visible in your App upon load. This may be an integer from 1 to 50. If this parameter is not specified, defaults to initialNumVisible.  For example: If your Collection includes 100 active and 100 legacy comments, set initalNumVisible:10, and initialNumVisibleLegacy:5, to display 10 active comments (with a  Show More  button) + 5 archive comments (with a  Show More  button).|
|**maxVisible**|*optional* integer |Sets the maximum number of visible pieces of top-level content in the Chat App. If new pieces of content stream in, content at the bottom of the stream will be removed from the page. If the  Show more…  button is clicked, the parameter is ignored and the user is free to show as much content as desired. (Use this parameter to control the number of items that appear on the page in high velocity streams.)|
|**postToButtons**|*optional* array |Used to configure which providers appear when embedding the Live Blog App. Available options are  tw  (Twitter),  fb  (Facebook), and  li  (LinkedIn). Defaults to [  tw ,  fb ].|
|**readOnly**| *optional* boolean|Disables all interactivity for the Collection. When true, users will be unable to log into the stream, and unable to Post, Edit, Reply to, or Like content. When true, users will be able to Flag and Share content. Default is false.|
|**stream**| *optional* object|Contains options to configure streaming of the App.|
|**stream.catchup**| *optional* integer|Specifies the number of seconds previous to the present moment that the stream should load. By default, Livefyre loads 50 pieces of content, and then loads all content submitted between those and the present time. In very fast use cases, content may be posted too quickly to allow the App to ‘catch up’ to the present. Use this setting to define the number of seconds previous to now for which content will be posted (after the initial content load).|
|**stream.delay**| *optional* integer|Specifies the number of seconds between streaming requests. Use this parameter to help control the flow of content and delay how often the DOM is updated.  Note:  If set too large, the stream may fall behind.|


>[!NOTE]
>
>You can pass one or more `convConfig` objects during App initialization to display multiple Apps on the same page. Be aware that extra Apps use browser resources and performance may degrade as the number increases.

## CollectionMeta Object {#c-collectionmeta-object}

The `CollectionMeta` object is a JSON object that specifies metadata to store within the Collection. 

`CollectionMeta` is always encoded before being passed to Livefyre for security. The encoded value is passed into the `ConvConfig` object shown above.

>[!NOTE]
>
>You must add server-side code to encode the `CollectionMeta` JSON object. See Building Server-side Tokens for more information.

|Parameter|Type|Description|
|--- |--- |--- |
|**articleId**|*required* string |A unique ID for the Collection.|
|**title**|*required* string |The title you wish to apply to the Collection. This often corresponds to the title of the page that displays the App.  For example: “Integration is So Much Fun!” <br>**Note:**  The max character length for the title is 255 characters. The title field does not support HTML entities. Please encode special characters using UTF-8.|
|**url**| *required* string|The canonical absolute URL you wish to attach to this Collection. This URL will be used to generate links back to the App from content shared on Facebook and Twitter, email notifications, and Livefyre Studio.  <br>**Note** Livefyre requires the use of a fully qualified domain name; the port number or a callback to resolve the local setup is not required. If testing locally, be certain to use a valid base URL domain. <br>For example: `https://customer.com` is valid, while `https://localhost:5995` is not. Once you have set up your local webserver to accept a fully qualified domain name, no callbacks or resolutions are needed, and local development can proceed as expected.|
|**type**| *required* string|The Collection type. Must be `livechat`.|

The `CollectionMeta` object may also contain the following optional parameter: 

|  Parameter  | Type  | Description  |
|---|---|---|
|  **tags** | *optional* string  | A comma-separated list of single keywords or phrases. Search Collections by tags within Studio or with the search API. <br> **Note:** While tags added through Studio may contain spaces, tags entered through the API cannot. Use underscores to define tags that will display spaces in the UI. (For example: use `Monday_Quarterback` to display Monday Quarterback in Studio.)  |

## Adding an Event Handler {#concept_06D8B811C98B4CC6B38C6340EBA176E5}

To register event handlers, use the widget.on call within the App's callback function.

### For example

```
Livefyre.require(['fyre.conv#3'], function(Conv) { 
   new Conv(networkConfig, [convConfig], function(widget) { 
      widget.on('<strong><eventName></strong>', function (data) { 
         // Do something, perhaps using data 
      }); 
   }); 
});
```
