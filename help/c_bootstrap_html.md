---
description: Make community content available to search engine crawlers.
seo-description: Make community content available to search engine crawlers.
seo-title: Bootstrap HTML
solution: Experience Manager
title: Bootstrap HTML
uuid: 22e99a9f-377e-4883-899c-0d035bbb834d
index: y
internal: n
snippet: y
translate: y
---

# Bootstrap HTML

Make community content available to search engine crawlers.

For a complete list of available endpoints, please see the Livefyre [API Reference](http://livefyre-devhub-production.herokuapp.com/developers/api-reference/) section.

Livefyre Apps require that you execute JavaScript on your page to display content for your Collections. Because most search engine crawlers cannot execute JavaScript, they are unable to see the content that your community posts. Use the Bootstrap HTML API to add searchable fragments of this content to the initial HTTP response of your page, allowing your content and keywords to improve your search engine optimization.

>[!NOTE]
>
>This API is available only for Comments and Live Blog Collection types.

## Integration {#section_ryy_fqj_11b}

Livefyre’s Bootstrap HTML API will return an HTML fragment of your user content, that may be included in the page’s HTTP response. This response will be readable by search engine crawlers without executing any JavaScript. Once the page is live in a user’s browser, the HTML fragment will be replaced with the full, interactive widget, and the user will be able to post content.

To implement the Bootstrap HTML API:

1. Make a server to server API request to the Bootstrap HTML endpoint documented below.

   >[!NOTE]
   >
   >If you’re trying to grab the Bootstrap HTML for a conversation that does not yet exist (that is, if you have yet to embed the App or create the Collection), you will receive a 200, but with content that looks something like: `<!- HTTP 404 /example.fyre.co/000000/MTEwMTo2NDEyOD1RS/bootstrap.html ->`

1. If your return does not include content with a “404” in it, save it into a string. You may cache this response for later use to avoid requesting the Bootstrap HTML API on every pageload.
1. Insert the Bootstrap HTML string into your webpage where you’d like the content to appear.
1. Serve your webpage to the browser (or search engine crawler).

## Resource {#section_ezj_2qj_11b}

```
GET https://{networkName}.bootstrap.fyre.co/bs3/{networkName}.fyre.co/{siteId}/{base64 encoded article ID}/bootstrap.html 

```

## Parameters {#section_y34_dqj_11b}

* ** networkName ** Your Livefyre provided network name. For example: *labs* in labs.fyre.co.

* ** siteId ** The Site ID of the Collection.

* ** b64articleId ** The Article ID of the Collection using the base64url encoding.

## Example {#section_k5z_bqj_11b}

```
https://labs.bootstrap.fyre.co/bs3/labs.fyre.com/4/NTg0/bootstrap.html 

```

## Response {#section_e5t_zpj_11b}

```
https://gist.github.com/ec5c2457322faf9cf515 

```

