# gfz-map
 private repo for GFZ map

## Issues 
* !!! Use fitBounds() instead of center and zoom.

## Notes
* If the position of markers looks off, it's because the position is set to the *center* of the icon, so you need to set an y-offset to move the tip of the pin to the center.

## Features 

### Background map (basemap)
There are two ways of implementing the basemap.

#### Method 1 (simple)
The most barebones version is Openstreetmap's Lightgray base map (`OSM:LightGray:Base`): 
1. Register at [arcgis](https://www.arcgis.com/index.html).
2. Create an API key on [arcgis](https://www.arcgis.com/index.html) (i.e. a password that allows us to use the map hosted on their servers. I am not sure if it's possible to save it as a local file.)
3. use the `apiKey` in the snippet below.

```js
const apiKey = "KEY_GOES_HERE";
const basemap_id = "OSM:LightGray:Base";
L.esri.Vector.vectorBasemapLayer(basemap_id, {
    apiKey: apiKey
}).addTo(map);
```
#### Method 2 (more customisable)

However, if the map needs to be customised, then we also need to:

4. Create and store a map on [arcgis](https://www.arcgis.com/index.html). The map on this website is fairly customisable, but will take a while longer to load. 
5. Create an API key on [arcgis](https://www.arcgis.com/index.html) (i.e. a password that allows us to use the map hosted on their servers. I am not sure if it's possible to save it as a local file.)
6. Change the `basemap_id` and `apiKey` mentioned above to the  

Uses a **modified** version of Openstreetmap's Lightgray base map (`OSM:LightGray:Base`).

## Markers

Markers are currently font-awesome's markers. To see their free markers: https://fontawesome.com/search?m=free&s=solid%2Cbrands

## Layers Control

https://leafletjs.com/SlavaUkraini/examples/layers-control/