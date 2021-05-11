# MODULE 13: JS & APIs
In this module, you will use the Leaflet.js Application Programming Interface (API) to populate a geographical map with GeoJSON earthquake data from a URL. Each earthquake will be visually represented by a circle and color, where a higher magnitude will have a larger diameter and will be darker in color. In addition, each earthquake will have a popup marker that, when clicked, will show the magnitude of the earthquake and the location of the earthquake.

What You Will Learn
By the end of this module, you will be able to: 

- Create a branch from the main branch on GitHub.
- Add, commit, and push data to a GitHub branch.
- Merge a branch with the main branch on GitHub.
- Retrieve data from a GeoJSON file.
- Make API requests to a server to host geographical maps.
- Populate geographical maps with GeoJSON data using JavaScript and the Data-Driven Documents (D3) library.
- Add multiple map layers to geographical maps using Leaflet control plugins to add user interface controls.
- Use JavaScript ES6 functions to add GeoJSON data, features, and interactivity to maps.
- Render maps on a local server.

---
## Use `JavaScript's` `Leaflet` library and `Mapbox API` to create visualizations of earthquake data from the U.S Geological Survey

### Topics Covered:
- Retrieve data from a GeoJSON file.
- Make API requests to a server to host geographical maps.
- Populate geographical maps with GeoJSON data using JavaScript and the Data-Driven Documents (D3) library.
- Add multiple map layers to geographical maps using Leaflet control plugins to add user interface controls.
- Use JavaScript ES6 functions to add GeoJSON data, features, and interactivity to maps.
- Render maps on a local server.

---
# 13.1.2 Project Overbiew
Basic Project Plan
Purpose
The purpose of this project is to visually show the differences between the magnitudes of earthquakes all over the world for the last seven days.

Tasks
To complete this project, use a URL for GeoJSON earthquake data from the USGS website and retrieve geographical coordinates and the magnitudes of earthquakes for the last seven days. Then add the data to a map.

Approach
Your approach will be to use the JavaScript and the D3.js library to retrieve the coordinates and magnitudes of the earthquakes from the GeoJSON data. You'll use the Leaflet library to plot the data on a Mapbox map through an API request and create interactivity for the earthquake data.

Now that you have an overview of the project plan, let's set up a Mapbox account and get the API token you'll need to create geographical maps.

# 13.2.1
The Mapbox API
Before you create any maps, you'll need to create a Mapbox account and get your access token. Sadhana is going to give you access to the company Mapbox account so you can create your own API key.
Mapbox provides custom maps for websites and applications such as Strava, Facebook, the Financial Times, The Weather Channel, Snapchat, and Instacart. Since October 2019, Mapbox has been generating up to 14 billion individual sensor readings daily across 100,000 map updates on connected devices.

To get started, register for a Mapbox account and get an API key.

Create a Mapbox Account
Follow the steps below to register for a Mapbox account and generate your API key so that you can render maps on the browser. Once you create an account, copy the access token and keep it somewhere safe.

The following video walks you through the process of creating your Mapbox account and generating your API key.



NOTE
Refer to Mapbox's pricing (Links to an external site.) for more options.

Now that you have your Mapbox API key, Sadhana will walk you through how to create a branch off the main branch where you'll add the code to create a simple map.