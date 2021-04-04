---
description: Plot user content to an interactive map.
seo-description: Plot user content to an interactive map.
seo-title: Map
solution: Experience Manager
title: Map
uuid: 1c3e399d-a610-4b80-a3b2-a5502b31480d
exl-id: 836b475e-0ec6-49f8-b89f-3af3209cf1f2
---
# Map{#map}

Plot user content to an interactive map.

Map allows you to stream geotagged content onto a world map, allowing you to locate the social buzz around breaking news or a live event. All applicable content will be displayed, including text, comments, photos, and Tweets.

>[!NOTE]
>
>Maps are powered by [©OpenStreetMap](https://www.openstreetmap.org/copyright), which provides the data Livefyre uses to render its Maps.

## Integration {#section_w2m_db2_d1b}

The quickest way to use Map is to use the built version hosted on Livefyre’s CDN.

First, add [Livefyre.js](https://github.com/Livefyre/Livefyre.js) to your page.

```
<script src="https://cdn.livefyre.com/Livefyre.js"></script> 

```

Then, position the element in which the Map App will appear.

```
<div id="map" style="height: 500px;"></div>
```

Finally, use Livefyre.require to construct the Map, and get a Collection to pipe in from streamhub-sdk. Keep in mind that Map can show only Content with geotagged metadata. Twitter and Instagram Curate support this feature. To ensure best performance, include a geolocation filter on all of your Curate Rules for the Collection.

```
<script> 
Livefyre.require(['streamhub-map#1', 'streamhub-sdk#2'], 
function (Map, SDK) { 
    var map = new Map({ 
        el: document.getElementById('map') 
    }); 
    var collection = new SDK.Collection({ 
        network: 'strategy-prod.fyre.co', 
        siteId: 340628, 
        articleId: 'custom-1389845009515' 
    }); 
    collection.pipe(map); 
}); 
</script>
```

Check out this [live example](https://codepen.io/cheung31/pen/wkmbF).

## Configuration {#section_jc5_gxb_c1b}

`initial`

The initial number of items to load from the Collection and display on the map. After this number are loaded, users may click a button to show more. (Optional. Defaults to 50.)

```
var map = new Map({ 
    el: document.getElementById('map'), 
    initial: 100 
});
```

`leafletMapOptions`

Options to pass to the underlying [Leaflet](https://leafletjs.com/) map, which Map uses for rendering. Use this option to set [Leaflet Map Options](https://leafletjs.com/reference.html#map-options), including the initial centerpoint of the map, and initial and maximum zoom levels. (Optional.)

```
var map = new Map({ 
    el: document.getElementById('map'), 
    leafletMapOptions: { 
        center: [37.774, -122.4], 
        zoom: 15 
    } 
});
```
