# Digital vs Web Map
While we’re talking about maps loading and working in the web, let’s talk the difference between a digital map and a web map. The term digital map is used quite often. As a benchmark, Wikipedia’s entry for “Digital Mapping” is:

The process by which a collection of data is compiled and formatted into a virtual image.

### Digital and Scanned Maps
More specifically to our workshop, a digital map is a map that was somehow derived from a computer. Sometimes we use this term to refer to scanned paper maps which are scanned and reformatted into digital images of maps.
More commonly, we use this term for “born digital” maps like this cycling map from the City of Vancouver. This map was likely constructed with geospatial data and a Geographic Information System (GIS), and published at a static scale and dimension.

### Web Maps
Web maps are a means of visualizing and interacting with geographic data. Following the definition above, a web map is a type of digital map since it is derived from a computer. However, there are some important differences:

Dynamic scales and content Web maps are not static images. Different scales display varying levels of detail. For instance, zooming in may reveal information that wasn’t apparent before. For this reason, web maps are not designed for print.

Interactive Web maps are built to be interacted with by an end user, often in order for the user to explore a dataset and learn something. Take for example Climate Central’s Surging Seas Risk Zone Map. Or, listen to the radio anywhere in the world with radio.garden

Display real-time data updates Web maps are useful for geovisualizing real-time data like weather. Watch the wind blow across the country.
Often relies on web and mobile technology

Web maps are ubiquitous - we see and use them all the time. For example, Google Maps. For small businesses, web maps are helpful for finding directions. For app builders, web maps might provide a method for routing to locations using a mobile device’s geolocation features. For researchers, they may help communicate important information in an area of study. For journalists, they may give spatial context to a story like where Amazon locates its warehouses and why.

## Raster Data
Raster data is made up as a matrix of pixels, also referred to as cells in much the same way as you might find when working within a spreadsheet. They are often square and regularly spaced but don't have to be. Think of walking over a field divided into a grid of squares with each square representing a value which can be discrete (e.g. soil type) or continuous (e.g. elevation).

## Vector Data
Rather than working with a matrix of cells, vector data stores basic geometries (made up of one or more interconnected vertices), with three key types:
- Points - single vertex, e.g. a house.
- Lines - two or more vertices where the first and last vertex are not equal, e.g. a road.
- Polygons - three or more vertices with the last vertex equal to the first, e.g. a boundary.

# Basic Components 

### Tiles
Map tiles are squares of geographic data that are loaded to your frame of view whenever you zoom or pan your map. Each tile is 256px by 256px (traditionally a .png image at roughly 20-40kb each), making them quick to load over an internet connection. These tiles provide a geographic reference for other data layers that you might add later (we’ll get to that in a minute). You’ve probably noticed them if you’ve had choppy internet connection and had to wait for data to load:

Every time you pan your map, new tiles are loaded to fill that frame of view. The tiles outside of that view are not loaded because loading the entire world’s tiles would be time consuming, especially if you were just focused on a small area. When you zoom in or out, new tiles are loaded to correspond with the level of detail needed at each zoom level.

### Zoom Levels
Because web maps refresh content as you zoom in, they don’t have a traditional map scale. Instead, there are different levels associated with the amount of detail shown on the map. Web maps typically have around 20 zoom numbered levels. Zoom level 0 has the least amount of detail, and is from a viewpoint as far away as earth as it gets. As the zoom level number goes up, so does the detail. Zoom level 18 has enough detail that displaying building labels makes sense without a mess (imagine what building labels would look like on a web map zoomed all the way out!). Zoom level 0 consisting of only 1 tile for the entire world (this zoom level loads the fastest!). Zoom level 18 consists of around 69 billion tiles. That’s a lot of data!!!!

### Tile Servers
You might be thinking: Where are all these tiles loading from? Well, there are services that render these tiles for consumption. The main two are Google and OpenStreetMap, but there are many others.

You might also be thinking: Can I customize my own tiles to make them look cool? You can, with services like Mapbox Studio. Or you can set up your own server to render your own.
