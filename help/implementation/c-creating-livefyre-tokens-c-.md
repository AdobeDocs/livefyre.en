---
description: Learn how to generate Livefyre tokens using the `C#` language.
seo-description: Learn how to generate Livefyre tokens using the `C#` language.
seo-title: Creating Livefyre Tokens `C#`
solution: Experience Manager
title: Creating Livefyre Tokens `C#`
uuid: c5e05625-8550-4b51-9211-134600e20ec7
exl-id: 6360c325-0c3f-4ecb-90f7-951ef4e6f410
---
# Creating Livefyre Tokens C\# {#creating-livefyre-tokens-c}

Learn how to generate Livefyre tokens using the ``C#`` language.

You can leverage legacy documentation and sample code to use `C#.NET` to write methods to create tokens.

To reference Livefyre’s official libraries, use the [Java Library](https://github.com/Livefyre/livefyre-java-utils) as a starting point for `C#` developers.

You may also consider using the [Node.js Library](https://github.com/Livefyre/livefyre-nodejs-utils) from the command line to generate reference tokens for yourself, and to get familiar with the method structure.

* [Jump to Collection Meta Token](https://gist.github.com/gibron/56cb9c7060bf4816c4c5#the-collectionMeta-token)
* [Jump to Auth Token](https://gist.github.com/gibron/56cb9c7060bf4816c4c5#the-auth-token)

## Dependencies {#section_c15_fnh_xz}

* You will need the [JWT nuget package](https://www.nuget.org/packages/JWT) in your project in order to generate the tokens.
* Code samples on this page use the [Newtonsoft JSON](https://www.nuget.org/packages/newtonsoft.json/) package.

## CollectionMeta Token {#section_dzt_4mh_xz}

The CollectionMeta Token is passed to Livefyre when you embed Comments on a page, and provides our system with the necessary metadata for your new collection. In addition, you will create an MD5 `checksum` of this data, which Livefyre checks to see if the metadata has changed. (e.g. if the title or url of your article was edited).

This token is signed with your `Site Key`, which was provided to you by your Techncial Account Manager at Livefyre.

See also:

* Official CollectionMeta Token Docs
* [Example Gist](https://gist.github.com/pcolombo/dbbea020618c521a2bd5)

1. Build a Dictonary containing the metadata for the collection. We’re only going to add some of the necessary fields in this step, becuase we want to create a checksum of this object BEFORE we add the articleId.

   ```
       // Site Key provided by Livefyre 
       string siteSecret = "ABCDE1234"; 
     
       var meta = new Dictionary<string, object>() { 
           {"title", "Kings win the Stanley Cup"}, 
           {"url", "https://www.website.com/kings-win-stanley-cup"}, 
           {"tags", "sports, hockey, stanley_cup"}, 
           {"type", "livecomments"} 
       };

   ```

    * **title** *required*:  The title of the collection, typically the title of your article. Max length is 255 characters. Does not support html entities. Please encode special characters using UTF-8.
    * **url** *required*:  The canonical url of your article. This is used by the comment sharing and social sync features, and links to your article from the Admin dashboard. If testing locally, please note that Livefyre will not accept ‘localhost’ as a domain.
    * **tags** *optional*:  A comma-separated list of tags you would like to add to the collection in the Livefyre dashboard. Tags cannot contain spaces. Use underscores if you wish a space to appear in the Admin dashboard.
    * **type** *optional*:  A string indicating what type of collection to create. Valid values are:

        * `reviews`
        * `sidenotes`
        * `ratings`
        * `counting`
        * `livecomments`
        * `liveblog`
        * `livechat`

      If not specified, a LiveComments collection is created by default.

1. JSON encode this dictionary, and generate an md5 checksum of it.

   ```
          var metaStr = JsonConvert.SerializeObject(meta); 
       byte[] hash; 
     
       using (var md5 = MD5.Create()) 
       { 
           hash = md5.ComputeHash(Encoding.UTF8.GetBytes(metaStr)); 
       } 
     
       StringBuilder sBuilder = new StringBuilder(); 
     
       // Loop through each byte of the hashed data  
       // and format each one as a hexadecimal string  
       for (int i = 0; i < hash.Length; i++) 
       { 
           sBuilder.Append(hash[i].ToString("x2")); 
       } 
   
   ```

1. Add the **articleId** to the Dictionary. The **checksum** does not go into the collectionMeta token, but should be sent as a seaprate parameter in the convConfig js object.

   ```
       meta.Add("articleId", "article-abcde00001"); 
   
   ```

    * **articleId** *required*:  A unique identifer for your collection within your Livefyre site. Typically, the unique articleId used in your CMS. (e.g. your WordPress post ID) This value should never change. Livefyre identifies unique collections by the combination of siteId and articleId.

1. Generate a signed JWT Token of the Dictionary, using the Site Key provided to you by Livefyre. Please note that you must specify the correct hash algorithm, as the JWT package does not use HS256 by default.

   ```
       string token = JWT.JsonWebToken.Encode(meta, siteSecret, JWT.JwtHashAlgorithm.HS256);
   ```

## The User Auth Token {#section_g1d_43h_xz}

The User Auth Token is used to sign a user into Livefyre. When a user signs into your site, the site generates a User Auth Token that is passed to the Livefyre widget on the page. (For more information on the authentication process see Remote Profiles.)

This token requires your Network name (network.fyre.co), and is signed with your Network Key which is provided to you by your Technical Account Manager at Livefyre.

See also:

* Official Auth Token Docs
* [Example Gist](https://gist.github.com/pcolombo/7d7403172c28734c87e2)

1. Build a Dictonary containing the necessary information.

   ```
       string networkKey = "ABCDEF1234"; 
     
       var payload = new Dictionary<string, object>() {  
               { "domain", "mynetwork.fyre.co" }, 
               { "user_id", "user-00001" }, 
               { "expires", DateTime.Now.AddDays(7).Ticks }, 
               { "display_name", "johndoe" } 
           }; 
    
   ```

    * **domain:** The name of your network (provided by Livefyre.) e.g mynetwork.fyre.co
    * **user_id:** The unique user id for the user in your site’s profile system. Must be alphanumeric characters only (A-Z, a-z, 0-9). If your systems user id’s contain invalid charaacters, consider sending Livefyre an md5 hash of the user id, or a base64 encoded version of it. (Let your account manager know if you do this.)
    * **expires:** The date (in Epoch time) that the token expires. This should match the session time of logins on your site, so that Livefyre’s signed-in state stays in sync with your site’s signed-in state.
    * **display_name:** The user’s display name in your profile system, as it should be displayed in the comment stream.

1. Generate a signed JWT Token of the Dictionary, using the Network Key provided to you by Livefyre. Please note that you must specify the correct hash algorithm, as the JWT package does not use HS256 by default.

   ```
          string token = JWT.JsonWebToken.Encode(payload, networkKey, JWT.JwtHashAlgorithm.HS256);
   ```
