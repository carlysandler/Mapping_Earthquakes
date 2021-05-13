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

13.2.2
Create a Branch on Your Repository
Before you add your folders and files to the Mapping_Earthquakes folder, Basil would like you to create a GitHub branch for the basic map. Basil informs you that creating a branch off the main branch allows you to create a new feature, or change some part of the original code. Once he has reviewed your code on your branch, Sadhana will show you how to merge it with the main branch.
Branching makes it possible to create an isolated environment when creating a new feature, or to correct an issue in the main code no matter the scope.

Creating branches off the main branch is where Git shines. A branch allows you to make changes to the main code "off to the side," like a branch on a tree. Once the code on the branch has been reviewed and approved, only then can the branch be merged into the main branch. This ensures that the main branch always contains production-quality code.

Before we create a branch and add files to the new branch, make sure your copy of the main branch on your computer is up to date with the main branch on GitHub.



It's a best practice to either "pull" from the main branch to get the latest changes to the main branch, or pull "upstream" of the branch you are creating. This is important because your version of the main branch on your computer needs to be up to date with the main branch on GitHub.

Follow these steps to create a branch:

Navigate to the repository folder on your computer.
In Terminal on macOS or Git Bash on Windows, type git pull or git pull origin main and press Enter.
Type git checkout -b Simple_Leaflet_Map and press Enter.
git checkout lets us navigate between branches.
-b indicates we are creating a new branch.
The name of the new branch follows -b.
After pressing Enter, your terminal or Git Bash should return the following:

Switched to a new branch 'Simple_Leaflet_Map'
Now we are in the Simple_Leaflet_Map branch. Confirm this by typing git branch and pressing Enter. The output in Terminal or Git Bash should look as follows, with an asterisk next to the branch name:

* Simple_Leaflet_Map
  main
At this point, the folder structure on your computer hasn't changed. The files you had in your main branch are now in your Simple_Leaflet_Map branch. Visually, the repository should look like the following:

A visualization shows the main files in the Simple_Leaflet_Map
branch on
GitHub.

Next, we'll create a folder structure and write the code to create a simple map. When we are done, Sadhana will show us how to add folders and files to the Simple_Leaflet_Map branch.

# 13.2.3
Create an HTML Page and CSS File
Now that you have your API token and your branch is set up, Sadhana will let you get familiar with the documentation for using Leaflet. Then, she's suggested you jump in and create an HTML and CSS file and add links to some stylesheets in the HTML file.
Let's get familiar with Leaflet. Leaflet has a few links and simple HTML code that we will add to an index.html page.

The Leaflet JavaScript Library
On the Leaflet (Links to an external site.) homepage, scroll midpage and click the Leaflet Quick Start Guide (Links to an external site.) link:

From the Leaflet homepage, click the "quick start guide"
link.

The Leaflet Quick Start Guide provides steps for setting up a Leaflet map. To begin, scroll midpage to the "Preparing your page" section:

Follow the "Preparing your page"
instructions.

The "Preparing your page" section includes links and HTML code that we'll add to our index.html page. First, we'll create a folder structure for our earthquake map webpage.

Create an HTML Page
Open your Mapping_Earthquakes repository folder in Visual Studio Code (VS Code). Create a new folder called "Simple_Map." Inside the folder, create a new index.html file. Next, create a template for your index.html file.

REWIND
To create a template for an html file, type an ! (exclamation point) and press Tab or Enter, and the empty file will be filled with the complete HTML5 boilerplate code.

Create a new index.html
file.

In our index.html file, we'll change the document title and add the code from the "Preparing your page" section.

Change the document title in the <title> element in the <head> section (<title>Document</title>) to "Leaflet-Basic-Map."

In the <head> section, just below the <title> element, add the following Leaflet CSS script from the "Preparing your page" section:

<!-- Leaflet CSS -->
<link rel="stylesheet" href="https://unpkg.com/leaflet@1.7.1/dist/leaflet.css"
integrity="sha512-xodZBNTC5n17Xt2atTPuE1HxjVMSvLVW9ocqUKLsCC5CXdbqCmblAshOMAS6/keqq/sMZMZ19scR4PsZChSR7A=="
crossorigin=""/>
In the body of our index.html file, add the Leaflet JavaScript script and id tag for the map inside a <div> element, as shown in the "Preparing your page" section:

<!-- Leaflet JavaScript -->
<script src="https://unpkg.com/leaflet@1.7.1/dist/leaflet.js"
integrity="sha512-XQoYMqMTK8LvdxXYG3nZ448hOEQiglfqkJs1NOQV44cWnUrBc8PkAOcXy20w0vlaXaVUearIOBhiXZ5V3ynxwA=="
crossorigin=""></script>
The Leaflet CSS and JavaScript files we added to the index.html file are referred to as content delivery networks (CDNs). Using CDNs has a security risk. To avoid the security risk, it's a best practice to include an integrity value with the CDN. Each file we added has its own integrity value, which is a Base64-encoded cryptographic hash of a resource that prevents the CDN from being hacked.

NOTE
For more about the Subresource Integrity value, please see the documentation on the Download Leaflet webpage (Links to an external site.) and Mozilla Developers' Subresource Integrity webpage (Links to an external site.).

Above the Leaflet JavaScript link script, add the following <div> element with the id tag for the map:

<!-- The div that holds our map -->
<div id="mapid"></div>
After adding the Leaflet CSS file, JavaScript file, and the <div> element with theid tag for the map, our index.html file should look like the following:

The index.html file Leaflet-Basic-Map contains the Leaflet CSS script
in the head section with the Leaflet JavaScript script and the id tag
for the map in the
body.

IMPORTANT
Make sure you copy and paste the Leaflet CSS file and JavaScript script from the website as they appear. Do not edit the script by deleting empty spaces. This will prevent that script from working on the index.html file, resulting in the map not being shown on the webpage.

Next, we will modify our #mapid to be set at a specific height using CSS code. To do this, we'll need to create a style.css file.

Create a CSS File
Before we create a style.css file, we'll need to create a folder for the file. In VS Code, create a new subfolder called "static" in our Simple_Map folder. In this folder, create another subfolder named "css." In the css folder, create a new file and name it style.css:

The VS Code File Explorer shows the new style.css file in the css
folder.

Next, add the following CSS code to our style.css file to set the style for our map on our index.html page and save the file:

html,
body,
#mapid {
  width: 100%;
  height: 100%;
  padding: 0;
  margin: 0;
}


At this point, your folder should look like the following:

The VS Code File Explorer shows the css folder inside the static
folder and the style.css file with a script in the css
folder.

Finally, we need to tell our index.html page to use the style.css file we created.

In the <head> section of our index.html page, add the following CSS link script below the Leaflet CSS and before the closing </head> element:

<!-- Our CSS -->
  <link rel="stylesheet" type="text/css" href="static/css/style.css">
Next, we'll create the code for a simple map.

# 13.4.1
Map a Single Point
Creating a simple Leaflet map was relatively straightforward. Now Sadhana will show you how to add a single marker to a map and change the radius of the marker. However, she would like you to create a branch for adding points to a map for the GitHub repository so that new interns and employees can use this as a tutorial.
Now that we can create a simple Leaflet map, we can plot data on the map. First, let's create a new branch. Sadhana suggests that we name this branch "Mapping_Single_Points" since we'll map single points.

REWIND
Follow these steps to create a branch off of the main branch:

Navigate to your repository on your computer.
Make sure you're on the main branch by typing: git branch
If you're not on the main branch, type: git checkout main
Pull the changes from the main branch by typing: git pull
Create a new branch by typing: git checkout -b [name_of_your_new_branch]
In your new branch, we'll add a new folder inside the Mapping_Earthquakes folder. Since we're going to work with the same file names in the same folder structure, we'll use the same folder structure as we did for the Simple_Leaflet_Map branch.

Set up the folder structure as follows: 

Mapping_Single_Points
index.html
static
css
style.css
js
config.js
logic.js
The two files that we'll change most often are the index.html and the logic.js files. Also, we might add an external file in the js folder. After checking out the new Mapping_Single_Points branch, copy all files from your Simple_Leaflet_Map folder and add them to a new Mapping_Single_Points folder..

Next, push the latest changes to the Mapping_Single_Points branch to GitHub.

REWIND
Follow these steps to push changes to a new branch:

Type: git status
Add the folders and files by typing: git add .
Confirm the correct files will be added by typing: git status
Commit the changes by typing: git commit -m
Push the changes to the branch by typing: git push --set-upstream origin Mapping_Single_Points
After adding the folders and files to your Mapping_Single_Points branch, your repository should look like the following:

The GitHub webpage shows the status of the Mapping_Earthquakes repository in the Mapping_Single_Points branch.

Next, we'll edit the logic.js file to add single points or markers to the basic map.

Add a Marker to the Map
Adding a marker to our simple map requires only one line of code, found in the Leaflet Quick Start Guide (Links to an external site.), under the "Markers, circles and polygons" subheading. Below the map is a line of code that reads as follows:

var marker = L.marker([51.5, -0.09]).addTo(map);
We're going to edit this line of code with the latitude and longitude for Los Angeles, California, and add it to our logic.js file that we used to create a simple map.

Open up the logic.js file using VS Code and add the following line of code before our tileLayer()code, and save the logic.js file:

//  Add a marker to the map for Los Angeles, California.
let marker = L.marker([34.0522, -118.2437]).addTo(map);
Next, open the index.html file in your browser. Your map should look like the following:

Add a marker to the map for Los Angeles,
California.

Next, we'll change the marker to a circle.

Add a Circle to the Map
To change the marker on our map to a point or dot, we'll use the circle() function. The circle() function will place a circle on the map at the given coordinates. The syntax for using the circle() function follows:

L.circle([34.0522, -118.2437], {
   radius: 100
}).addTo(map);
When using the circle() function, the default is just a small dot on the map, but we want to adjust the radius so that it's bigger and easier to see. The radius for the circle() function is measured in meters.

For the code above, add a circle with a 100-meter radius over Central Los Angeles when we assign a value to the radius key in the circle() function.

Copy the code for the circle function and replace it with the marker() function we used previously. We're also going to zoom in to a level of 14 on the setView() method. After editing your logic.js file, it should look like the following:

Use the circle () function to create a circle with a 100-meter radius over Central Los Angeles.

When we open our index.html file in our browser, it will show a circle over Central Los Angeles.

The OpenStreetMap shows a circle with a 100-meter radius over Central Los Angeles.

Now test your skills in the following Skill Drill:

SKILL DRILL
Using the Leaflet documentation, create a light-yellow circle with black lines indicating a 300-meter radius of Central Los Angeles on a dark map.

Your map should look like the following:

The OpenStreetMap shows a light-yellow circle with black lines indicating a 300-meter radius of Central Los Angeles on a dark map.

Alternatively, we can create a circle using the circleMarker() function. The circleMarker() function measures the radius of the circle in pixels, with the default radius set at 10 pixels. The syntax for using the circleMarker() function follows:

L.circleMarker([34.0522, -118.2437]).addTo(map);
Let's create a light-yellow circle with black lines indicating a 300-pixel radius on a dark map. Edit your logic.js file from the previous Skill Drill by changing your circle()function to a circleMarker()function. Your logic.js file should now look like the following:

Use the circleMarker() function to create a light-yellow circle with black lines indicating a 300-pixel radius of Central Los Angeles on a dark map.

If you didn't get the correct map style in the Skill Drill, replace the "streets-v11" in our tileLayer() code with "dark-v10" to look like the following:

// We create the tile layer that will be the background of our map.
let streets = L.tileLayer('https://api.mapbox.com/styles/v1/mapbox/dark-v10/tiles/{z}/{x}/{y}?access_token={accessToken}'
Save yourlogic.js file and open your index.html file in our browser. The circle will show a 300-pixel radius of Central Los Angeles.

The OpenStreetMap shows a light-yellow circle with black lines indicating a 300-pixel radius of Central Los Angeles.

Wow! What a big difference between the circle()and circleMarker()functions.

Remember, it's a best practice to commit early and often! Before you commit your code for the Mapping_Single_Points branch to GitHub, check to see if all the files will be tracked in the branch.



In the Mapping_Single_Points branch on the command line, type git status and you'll see that the logic.js file will be tracked:

data 13-4-1-mapping-single-points.png

Great job! Now, commit and push these files to the Mapping_Single_Points branch. Don't delete the branch, so that others can use it to learn how to map single points.

Next, Sadhana is going to show you how to add multiple locations to a map and change the radius of each marker.

NOTE
Use the links below to learn more about these Leaflet functions:

marker() function (Links to an external site.)
circle() function (Links to an external site.)
circleMaker() function

# 13.4.2
Map Multiple Points
Now that you have added a single marker to a map and changed some of the features of the marker, Sadhana wants you to iterate through an array of objects and map them. Other employees really like the branches you created, so Sadhana would like you to create a new branch for adding multiple points to a map.
Before we plot multiple markers and points, Sadhana wants you to create a new branch for mapping multiple points.

Create a new branch called "Mapping_Multiple_Points" with the following folder structure:

Mapping_Multiple_Points
index.html
static
css
style.css
js
config.js
logic.js
Copy the necessary folders and files from your Mapping_Single_Points branch and add them to the Mapping_Multiple_Points folder.

Add Multiple Markers
When we added a single marker to our simple map, we assigned our marker variable to the Leaflet class marker() function. This function will only add one latitude and longitude to the map. To add more markers to the map, the latitudes and longitudes are usually nested in an array. To add a marker for each location, we have to iterate through the array and add each latitude and longitude to the map.

First, in the logic.js file, replace the marker variable (which we used to map one location) with the cities variable that references the five most populous cities array in the following code block. Then save the file:

// An array containing each city's location, state, and population.
let cities = [{
  location: [40.7128, -74.0059],
  city: "New York City",
  state: "NY",
  population: 8398748
},
{
  location: [41.8781, -87.6298],
  city: "Chicago",
  state: "IL",
  population: 2705994
},
{
  location: [29.7604, -95.3698],
  city: "Houston",
  state: "TX",
  population: 2325502
},
{
  location: [34.0522, -118.2437],
  city: "Los Angeles",
  state: "CA",
  population: 3990456
},
{
  location: [33.4484, -112.0740],
  city: "Phoenix",
  state: "AZ",
  population: 1660272
}
];
Next, we need to iterate through each city object and add each city location to the marker() function, which will, in turn, be added to the map.



Below the cities array, add the following code to iterate through the array. Inside the brackets, use the console.log() function to print each object in the array to the console:

// Loop through the cities array and create one marker for each city.
cities.forEach(function(city) {
 console.log(city)
});
Save the logic.js file and open the index.html file in your browser.

If we look at the console tab, we'll see that each object, or city, of the cities array is printed to the console.

A U.S. map has a Chrome console tab on the right showing each object in the cities array.

Now, add each city's location to the map by adding the location to the marker() function.



In the forEach() function, assign the city variable to each object of the cities.js file. Then, get the coordinates of each city by adding city.location in the L.marker() function. We can then add each location to the map with the addTo() function and pass themap object as the argument.

Add the following code to your logic.js file and save it:

// Loop through the cities array and create one marker for each city.
cities.forEach(function(city) {
    console.log(city)
    L.marker(city.location).addTo(map);
});
When you open the index.html file in your browser, the map will show a marker on each city in the cities array.

The OpenStreetMap has five markers for the five cities in the cities array: Los Angeles,Phoenix, Houston, Chicago, and New York City.

When handling large datasets, it's a best practice to have the data in an external file and refer to that file and dataset in the logic.js file.

Even though our cities array is not that large, let's create a new file in the "js" folder called cities.js. Cut the cities array data from the logic.js file, place it in the cities.js file, and save the file.

Next, in the logic.js file, where the cities array was located, add a variable and assign it to the cities array. Add the following code to the logic.js file:

// Get data from cities.js
let cityData = cities;
Now the cities array is assigned to the cityData variable, which means we'll need to replace cities with cityData in our forEach() function. Edit the forEach() function so that it looks like the following and save the logic.js file:

// Loop through the cities array and create one marker for each city.
cityData.forEach(function(city) {
    console.log(city)
    L.marker(city.location).addTo(map);
});
Now open the index.html in your browser to confirm these changes worked.

Uh-oh! Something went wrong, as shown in the following image: 

When there is an error in a file, a blank webpage appears instead of a map.



After you inspect the page using the DevTools, the console might have an error message that says Uncaught ReferenceError: cities is not defined. This means the cities array data can't be found.

To correct this error, in the body of the index.html file and before the path to the logic.js script, add a <script> file with the path to the JavaScript cities.js file, like this:

 <script type="text/javascript" src="static/js/cities.js"></script>
After adding the <script> file, the body of our index.html file should look like the following:

The body of the index.html file shows the path to the cities.js
file.

Now, when we open up the index.html in our browser, the map should look like it did before we created the cities.js file and edited thelogic.js and index.html files.

The OpenStreetMap has five markers for the five cities in the cities array: Los Angeles, Phoenix, Houston, Chicago, and New York City.

Bind a Popup to the Marker
To add data from each object in the cities array, we'll use Leaflet's bindPopup() method on the marker() function. According to the guidance in the Quick Start Guide (Links to an external site.)'s "Working with popups" section, we only need to add HTML code inside the parentheses of the bindPopup() method:

Follow the bindPopup() method guidance, found in the Quick Start Guide's "Working with popups"section.

In the logic.js file, edit the forEach function and add the bindPopup() method. Inside the parentheses of the bindPopup() method, we'll retrieve the name of the city, state, and population.

Edit the forEach function to look like the following, save the logic.js file, and open the index.html file in your browser:

// Loop through the cities array and create one marker for each city.
cityData.forEach(function(city) {
    console.log(city)
    L.marker(city.location)
    .bindPopup("<h2>" + city.city + ", " + city.state + "</h2> <hr> <h3>Population " + city.population + "</h3>")
  .addTo(map);
});
Now, when we click on each marker, it will show the name, state, and population of the city.

The OpenStreetMap has five popup markers for the five cities in the cities array: Los Angeles, Phoenix, Houston, Chicago, and New York City.When a city popup marker is clicked, it shows data, such as population.

Let's format the population with a thousands separator by using the toLocaleString() method on the city.population in the bindPopup() method, like this:

The logic.js file edited with code to format the population of each city with a thousands separator.

Now our popup markers have the population formatted with a thousands separator.

The popup marker for Houston with population data has been formatted with a thousands separator.

Next, change the marker for each city to a circle that has a radius equivalent to the city's population.

In the logic.jsfile, we'll replace the marker() function with the circleMarker() function in the forEach() function. Then we'll assign the "radius" key to the population by using city.population.

The forEach() function in our logic.js file should look like the following:

The logic.js file is edited with code to format the population of each city with a thousands separator and add circle the size of the population.

After you save the logic.js file and open the index.html file in your browser, your map will look like the following:

The OpenStreetMap now has a blue background.

Well, that doesn't look like the map from before! If we click on that map, "Phoenix, AZ" and its population appear in a popup.

The OpenStreetMap has a blue background and a popup marker for Phoenix.

We know that the data is being loaded onto the map, but what is the problem?



The problem with the map is that the radii are too large and don't fit on the map. To fix this, we'll have to decrease each city's radius so the circle markers fit on the map. In the logic.js file, divide the city.population value by "100000" to look like this:

radius: city.population/100000
Now when we open the map in our browser, the radius for each city looks proportional to the population.

The OpenStreetMap shows five city circle markers for the five cities
in the cities array, where the radius is in proportion to each city's
population, formatted with a thousands
separator.

Congratulations on creating varying size circle markers with popup information!

SKILL DRILL
Edit the logic.js file to create an orange circle popup marker for each city, with a lineweight of 4, a radius where the population number is decreased by 200,000,  that's on a dark map. When you click on the circle, the popup should display the city, state, and the population formatted with a thousands separator.

Your map should look similar to the following:  The OpenStreetMap shows five circle markers on a dark map, where each circle is orange and has a radius where the population number is decreased by 200,000. Each popup marker shows the city, state, and population formatted with the thousands separator.

Next, Sadhana will show you how to plot lines on a map.

ADD/COMMIT/PUSH
Add, commit, and push your changes to the Mapping_Mulitple_Points branch. Don't delete the branch so that others can use it to learn how to map multiple points with popup markers.

NOTE
For more information, see the Leaflet documentation on the bindPopup() method (Links to an external site.).

# Basil and Sadhana are ecstatic that you can add multiple locations to a map. This will be highly beneficial when you need to add the earthquake data to a map. Now, Sadhana will walk you through how to add lines to a map.
On our Leaflet map, we can plot coordinates to create lines between locations, like transportation routes.

Before we plot lines on a map, let's create a new branch called "Mapping_Lines" that has the following folder structure:

Mapping_Lines
index.html
static
css
style.css
js
config.js
logic.js
Copy the necessary folders and files from one of your Mapping_Mulitple_Points branches and add them to the Mapping_Lines folder.

Map a Single Line
Adding lines to a map requires that the coordinates for the starting and ending points be a one-dimensional array with two elements: latitude and longitude. To illustrate how lines are mapped, let's map the airline route from Los Angeles to San Francisco. Mapping airline routes will help us understand how tectonic plate data is added to a map.

The starting point for our line will be the Los Angeles International Airport (LAX), with the coordinates [33.9416, -118.4085]. The ending point for our line will be the San Francisco International Airport (SFO), with the coordinates [37.6213, -122.3790].

When we create a line in Leaflet, the starting and ending points and all coordinates along the route need to be in an array. We can assign the array to the line variable like this:

// Coordinates for each point to be used in the line.
let line = [
  [33.9416, -118.4085],
  [37.6213, -122.3790]
];
Let's edit our logic.js file to create a line from LAX to SFO.

First, change the coordinates for the center of the map to somewhere between LAX and SFO by adding [36.1733, -120.1794] in the setView() method.
Change the zoom level in the setView() method to 7.
Add the code above for our line below the map variable for the center of the map.
Lastly, create a line on a map using the Leaflet polyline() function. Add the following line of code after the line variable:
// Create a polyline using the line coordinates and make the line red.
L.polyline(line, {
  color: "red"
}).addTo(map);
In the polyline() function, we pass the line coordinates and the key-value pair color: "red" to make the line red.

Save the logic.js file with the changes. It should look like the following:

The logic.js file edited with code to create a line between two
points.

When you open the index.html file in your browser, your map should have a red line between LAX and SFO.

The OpenStreetMap shows a red line from LAX to SFO.

Now we'll add a few more stops on our airline route.

Map Multiple Lines
Let's edit the logic.js file and add two more airport stops to our line variable: Salt Lake City International Airport (SLC) and Seattle-Tacoma International Airport (SEA). Follow these steps: 

Edit the line variable in the logic.js file so that it includes the two new sets of coordinates.

// Coordinates for each point to be used in the polyline.
let line = [
  [33.9416, -118.4085],
  [37.6213, -122.3790],
  [40.7899, -111.9791],
  [47.4502, -122.3088]
];
Make the line yellow by editing the value for the "color" key in the polyline() function to yellow.

// Create a polyline using the line coordinates and make the line black.
L.polyline(line, {
   color: "yellow"
}).addTo(map);
Change the map style to "satellite-streets-v11."

Finally, change the center of the map to SFO and change the zoom to 5 so that we can see the line.

// Create the map object with center at the San Francisco airport.
let map = L.map('mapid').setView([37.6213, -122.3790], 5);
After you save the logic.js file and open the index.html file in your browser, your map should look like the following, showing the route from LAX, SFO, SLC, and SEA:

The OpenStreetMap shows a yellow line joining LAX-SFO-SLC-SEA on a Satellite Streets map.

SKILL DRILL
Edit your logic.js to create an airline route from SFO to John F. Kennedy International Airport (JFK) with two stops, Austin-Bergstrom International Airport (AUS) and Toronto Pearson International Airport (YYZ). Make the route a blue dashed line, with a weight of 4 and opacity of 0.5 on the light map.

Hint: You'll need to find the coordinates for some of these airports.

Bonus: Add your city or another city as a stopping point.

Your map should look similar to the following:

The OpenStreetMap shows a blue dashed line from SFO to JFK with two stops, AUS and YYZ, on the light map.

Great job on mapping routes on your map!

ADD/COMMIT/PUSH
Add, commit, and push your changes to your Mapping_Lines branch. Don't delete the branch so that others can use it to learn how to map lines.

After you push your changes to the branch, Sadhana will show you how to plot data from a GeoJSON (.json) file.

NOTE
For more information, see the Leaflet documentation on the polyline() function (Links to an external site.).

# Basil and Sadhana are ecstatic that you can add multiple locations to a map. This will be highly beneficial when you need to add the earthquake data to a map. Now, Sadhana will walk you through how to add lines to a map.
On our Leaflet map, we can plot coordinates to create lines between locations, like transportation routes.

Before we plot lines on a map, let's create a new branch called "Mapping_Lines" that has the following folder structure:

Mapping_Lines
index.html
static
css
style.css
js
config.js
logic.js
Copy the necessary folders and files from one of your Mapping_Mulitple_Points branches and add them to the Mapping_Lines folder.

Map a Single Line
Adding lines to a map requires that the coordinates for the starting and ending points be a one-dimensional array with two elements: latitude and longitude. To illustrate how lines are mapped, let's map the airline route from Los Angeles to San Francisco. Mapping airline routes will help us understand how tectonic plate data is added to a map.

The starting point for our line will be the Los Angeles International Airport (LAX), with the coordinates [33.9416, -118.4085]. The ending point for our line will be the San Francisco International Airport (SFO), with the coordinates [37.6213, -122.3790].

When we create a line in Leaflet, the starting and ending points and all coordinates along the route need to be in an array. We can assign the array to the line variable like this:

// Coordinates for each point to be used in the line.
let line = [
  [33.9416, -118.4085],
  [37.6213, -122.3790]
];
Let's edit our logic.js file to create a line from LAX to SFO.

First, change the coordinates for the center of the map to somewhere between LAX and SFO by adding [36.1733, -120.1794] in the setView() method.
Change the zoom level in the setView() method to 7.
Add the code above for our line below the map variable for the center of the map.
Lastly, create a line on a map using the Leaflet polyline() function. Add the following line of code after the line variable:
// Create a polyline using the line coordinates and make the line red.
L.polyline(line, {
  color: "red"
}).addTo(map);
In the polyline() function, we pass the line coordinates and the key-value pair color: "red" to make the line red.

Save the logic.js file with the changes. It should look like the following:

The logic.js file edited with code to create a line between two
points.

When you open the index.html file in your browser, your map should have a red line between LAX and SFO.

The OpenStreetMap shows a red line from LAX to SFO.

Now we'll add a few more stops on our airline route.

Map Multiple Lines
Let's edit the logic.js file and add two more airport stops to our line variable: Salt Lake City International Airport (SLC) and Seattle-Tacoma International Airport (SEA). Follow these steps: 

Edit the line variable in the logic.js file so that it includes the two new sets of coordinates.

// Coordinates for each point to be used in the polyline.
let line = [
  [33.9416, -118.4085],
  [37.6213, -122.3790],
  [40.7899, -111.9791],
  [47.4502, -122.3088]
];
Make the line yellow by editing the value for the "color" key in the polyline() function to yellow.

// Create a polyline using the line coordinates and make the line black.
L.polyline(line, {
   color: "yellow"
}).addTo(map);
Change the map style to "satellite-streets-v11."

Finally, change the center of the map to SFO and change the zoom to 5 so that we can see the line.

// Create the map object with center at the San Francisco airport.
let map = L.map('mapid').setView([37.6213, -122.3790], 5);
After you save the logic.js file and open the index.html file in your browser, your map should look like the following, showing the route from LAX, SFO, SLC, and SEA:

The OpenStreetMap shows a yellow line joining LAX-SFO-SLC-SEA on a Satellite Streets map.

SKILL DRILL
Edit your logic.js to create an airline route from SFO to John F. Kennedy International Airport (JFK) with two stops, Austin-Bergstrom International Airport (AUS) and Toronto Pearson International Airport (YYZ). Make the route a blue dashed line, with a weight of 4 and opacity of 0.5 on the light map.

Hint: You'll need to find the coordinates for some of these airports.

Bonus: Add your city or another city as a stopping point.

Your map should look similar to the following:

The OpenStreetMap shows a blue dashed line from SFO to JFK with two stops, AUS and YYZ, on the light map.

Great job on mapping routes on your map!

ADD/COMMIT/PUSH
Add, commit, and push your changes to your Mapping_Lines branch. Don't delete the branch so that others can use it to learn how to map lines.

After you push your changes to the branch, Sadhana will show you how to plot data from a GeoJSON (.json) file.

NOTE
For more information, see the Leaflet documentation on the polyline() function (Links to an external site.).

# 13.5.2
Map GeoJSON Point Type
You meet with Basil and Sadhana to discuss your project. Basil informs you that the earthquake data you'll map will have the geometry type Point. Basil thinks it would be a good idea to learn to parse GeoJSON data that is similar to the earthquake data.
Sadhana wants you to practice mapping GeoJSON data that she will give you to add to your logic.js file. This will be a good introduction on learning how to access the data from a JSON file.

Before we map any data, let's create a new branch called "Mapping_GeoJSON_Points" and create the following folder structure:

Mapping_GeoJSON_Points
index.html
static
css
style.css
js
config.js
logic.js
Copy the necessary folders and files from one of your previous branches and add them to the Mapping_GeoJSON_Points folder.

Map a GeoJSON Point
First, we'll add single point on our map using GeoJSON data. The following GeoJSON data is a FeatureCollection object that has properties and geometry for the San Francisco Airport:

// Add GeoJSON data.
let sanFranAirport =
{"type":"FeatureCollection","features":[{
    "type":"Feature",
    "properties":{
        "id":"3469",
        "name":"San Francisco International Airport",
        "city":"San Francisco",
        "country":"United States",
        "faa":"SFO",
        "icao":"KSFO",
        "alt":"13",
        "tz-offset":"-8",
        "dst":"A",
        "tz":"America/Los_Angeles"},
        "geometry":{
            "type":"Point",
            "coordinates":[-122.375,37.61899948120117]}}
]};
Since we are going to add the San Francisco Airport to our map, let's change the center to the San Francisco Airport. Add the following code to our logic.js file to create the center of the map at the airport with a zoom level of "10."

// Create the map object with center at the San Francisco airport.
let map = L.map('mapid').setView([37.5, -122.5], 10);
In the GeoJSON example (Links to an external site.) given on the Leaflet page, we can see that the simple GeoJSON feature is similar to our sanFranAirport.

The Leaflet page provides an example of the GeoJSON
feature.

GeoJSON objects are added to the map through a GeoJSON layer, L.geoJSON(). In "The GeoJSON Layer" section, it says to create the GeoJSON layer and add it to our map. We can use the following code to do that:

L.geoJSON(geojsonFeature).addTo(map);
Let's edit this GeoJSON layer as follows:

// Grabbing our GeoJSON data.
L.geoJSON(sanFranAirport).addTo(map);
Also, add it to our logic.js file below the GeoJSON airport data and above the tileLayer()method. After you save the logic.js file, it should look like the following:

The logic.js file reflects our changing the center and zoom level of
the map, adding the GeoJSON data, and getting the GeoJSON
data.

NOTE
Please note that the coordinates appear in reverse order [-122.375, 37.61899948120117], compared to their order in the setView() method. This is because the GeoJSON data coordinates are set with the first parameter as X (longitude) and the second parameter as Y (latitude), as documented in the GeoJSON Standard. (Links to an external site.) The L.geoJSON()layer reverses the coordinates to plot them on the map.

Open the index.html file in your browser. Your map should have a marker at SFO.

The OpenStreetMap shows a marker on
SFO.

Later in this module we'll be using a URL to access a larger GeoJSON dataset to plot more points.

Bind a Popup to the Marker
REWIND
To display data on a map with a popup marker, we have to bind the marker with the GeoJSON layer, L.geoJSON(), using a callback function.

Our options to add data to a marker are to use the pointToLayer or onEachFeature callback functions. With either of these functions, we can add data to a map from each GeoJSON object. The major difference between the two functions is that the pointToLayer callback function adds markers to a map, whereas the onEachFeature callback function allows you to add styling and bind data to a popup marker.

Let's look at these two functions more closely.

The pointToLayer Function
For the pointToLayer callback function, the basic syntax for adding functionality to a marker follows:

L.geoJson(data, {
    pointToLayer: function(feature, latlng) {
      return L.marker(latlng);
     }
});
Let's break down what is happening in the L.geoJSON() layer:

We add two arguments: the data and the pointToLayer callback function.
The data will be our sanFranAirport data.
For the pointToLayer callback function, we are first going to call a function() where we pass each GeoJSON feature as feature, and its latitude and longitude as latlng.
Then we add a marker for each feature with a latitude and longitude in the pointToLayer callback function argument by using return L.marker(latlng).


Even though we have a marker on the previous map, let's edit our logic.js file to add a marker using the pointToLayer function and add data to a popup marker.

First, let's edit the logic.js file to add the pointToLayer callback function to the L.geoJSON() layer. To better understand what is passed with the feature argument in the function(), we will add feature in the console.log()function. Edit your L.geoJSON() layer code to look like the following:

// Grabbing our GeoJSON data.
L.geoJson(sanFranAirport, {
    // We turn each feature into a marker on the map.
    pointToLayer: function(feature, latlng) {
      console.log(feature);
      return L.marker(latlng);
    }

  }).addTo(map);
Save your logic.js file and open the index.html file in your browser. The map should look the same as it did before the edits. However, if we open the console on our developer tools, we will see that the feature is the JavaScript object geometry and properties of our GeoJSON object.

The Chrome console shows the JavaScript objects for the feature in the
pointToLayer callback
function.

Now, we'll add the data in the JavaScript objects to a popup marker.

REWIND
The properties in each JavaScript object can be accessed using the dot notation.



To add a popup marker, we need to use the bindPopup() method to the pointToLayer callback function. This will add a popup marker for each object in our GeoJSON data even though we only have one object in our data, SFO.

Let's add the city to the popup marker. In our logic.js file, after the return L.marker(latlng) in our L.geoJSON() layer, add the following code on the next line:

.bindPopup("<h2>" + feature.properties.city + "</h2>")
Using the dot notation, we can traverse through the JSON object to get the city by using feature.properties.city. Now, your logic.js file with L.geoJSON() layer should look like the following:

Use the pointToLayer function in the logic.js file to add a popup
marker to the
map.

Our map should look like the following, where a marker, when clicked, shows a city name:

The OpenStreetMap shows a popup marker for SFO with the city
name.

SKILL DRILL
Edit your logic.js to create a popup marker for San Francisco Airport on a night preview navigation map. When you click on the popup, it will display the city, state, and the name of the airport.

Your map should look like the following:

The OpenStreetMap shows a popup marker for SFO with the city and
state names appearing in the popup on a dark
map.

The onEachFeature Function
When we use the onEachFeature callback function we can add a popup marker for each feature and add data from the properties of the JavaScript object. The basic syntax for adding functionality to a marker follows:

L.geoJson(data, {
    onEachFeature: function(feature, layer) {
      layer.bindPopup();
     }
});
Let's break down what is happening in the L.geoJSON() layer:

First, we add two arguments: the data and the onEachFeature callback function.
The data will be our sanFranAirport data.
With the onEachFeature callback function we are first going to call an anonymous function, function(), where we pass each GeoJSON feature as feature, and any properties to the second argument, layer.
Let's edit our logic.js file to add a popup marker using the onEachFeature function. First, edit the logic.js file to add the onEachFeature callback function to the L.geoJSON() layer. To see what is passed with the layer argument in the anonymous function(), we'll pass layer in the console.log()function. Edit your L.geoJSON() layer code to look like the following:

Use the onEachFeature function in the logic.js file to add a popup
marker to the
map.

When we open our index.html file, the map will display a popup marker for SFO. When we open the console on our DevTools, we'll see that the layer returns many JavaScript methods that can be accessed and used, including the geometry and properties of our GeoJSON object.

The Chrome console shows the JavaScript methods
available.

SKILL DRILL
Edit your logic.js to create a popup marker for the San Francisco Airport on the outdoor map. When you click on the popup, it will display the airport code and name of the airport.

Your map should look like the following:

The OpenStreetMap shows a popup marker for SFO, with the airport
code and name in the popup
marker.

Great job on adding GeoJSON data to your map!

NOTE
For more information, see the Leaflet documentation on the L.geoJSON() layer. (Links to an external site.).

Next, we'll map multiple point type geometry from a JSON file.

# 13.5.3
Map Multiple GeoJSON Points
Now that you have a handle on how to map GeoJSON point type and add data to a popup marker, Basil and Sadhana want you to fetch GeoJSON data from a URL. After all, this is how GeoJSON data is usually accessed, and this is how you will access the earthquake data.
When mapping points, lines, and polygons, the data we use is accessed from a URL because this data is usually inaccessible for download or maybe too large to store on your computer and add as an external file.

Download the majorAirports.json file and put it on the Mapping_Earthquakes repository.

Download majorAirports.json (Links to an external site.)

Using the URL for the majorAirports.json file in your GitHub repository, we'll add multiple points onto a map.

When you click on the majorAirports.json file on GitHub, you should see an OpenStreetMap populated with major airports. Our map will look similar to this after we are done.

Launch the majorAirport.json file for a view of all major
airports.

Click the Raw button and the GeoJSON data will be loaded in the browser.

Click the Raw button to extract the GeoJSON data from the
majorAirport.json
file.

If the file size is large, it could take awhile to load on the page. Once it loads, it should look like the following:

Open the majorAirports.json file in the Chrome
browser.

To begin adding the data to the map, first we need to read the external majorAirports.json file.

REWIND
To read an external .json file, we need to use the d3.json() method. To use the d3.json() method, we need to have the <script src="https://d3js.org/d3.v5.min.js"></script> file in the index.html page.

Open the index.html file, and in the <head> section above the CSS link, add the following D3.js library file script:

<!-- d3 JavaScript -->
<script src="https://d3js.org/d3.v5.min.js"></script>
The <head> section of your index.html file should look like the following:

The index.html file includes the leaflet.css link, the d3 JavaScript,
and our CSS link in the head
section.

Next, we'll edit the logic.js file.

Change the geographical center of the map to the geographical center of the Earth and set the zoom level as follows:

// Create the map object with center and zoom level.
let map = L.map('mapid').setView([30, 30], 2);
Next, we'll access the majorAirports.json file on GitHub with the following airportData variable. Your URL may be different, but it should begin with https://raw.githubusercontent.com.

Add the following code after your tileLayer() method:

// Accessing the airport GeoJSON URL
let airportData = "https://raw.githubusercontent.com/<GitHub_name>/Mapping_Earthquakes/main/majorAirports.json";
NOTE
Having the tileLayer() method before accessing large datasets ensures that the map gets loaded before the data is added to it.

Next, we'll add the d3.json() method, which returns a promise with the then() method and the anonymous function().

Inside the d3.json() method we'll add the airportData variable.
Inside the anonymous function() we'll add the data parameter, which references the airportData.
We'll pass this data to the L.geoJSON() layer and then it'll be added to the map with addTo(map).
// Grabbing our GeoJSON data.
d3.json(airportData).then(function(data) {
    console.log(data);
  // Creating a GeoJSON layer with the retrieved data.
  L.geoJson(data).addTo(map);
});
Your logic.js file should look like the following:

The logic.js file includes code for accessing the airport.code and
adding a popup marker to the map using the pointToLayer
function.

Let's see how our map looks now. Open your index.html file in your browser using the command python -m http.server—just to be sure that the data is accessible through the Python server.

Your map should look like the following:

The OpenStreetMap shows markers for airports in the majorAirports.json
file.

SKILL DRILL
Edit your L.geoJson() layer to add a popup marker that displays all airports' codes and names.

Your map should look like the following: 

The OpenStreetMap shows popup markers listing all airports' codes
and
names.

Great job on adding multiple-point type GeoJSON data to your map. Next, Sadhana is going to show you how to add another map to the index.html file so you can toggle between two different maps.

# 13.6.1
Add Earthquake Data to a Map
Now that you know how to access GeoJSON data, parse the data, and add it to a map, Sadhana would like you to map all recorded earthquakes in the past seven days. Once you get the data, you'll add some features to the map to showcase the severity of earthquakes for viewers. 
As before, we need to set up a folder structure for our project in a new branch. Create a branch called "Earthquakes_past7days." Copy the folders and files from one of your previous branches and add them to the Earthquakes_past7days folder.



First, Sadhana wants you to rename the logic.js file to logicStep1.js. This way, each step has its own logic.js file that can be used by other interns in the future.

Now we'll edit our logicStep1.js file to create a map with all recorded earthquakes from the past seven days.

First, apply the streets and satelliteStreets map styles used for the GeoJSON polygon mapping. Change the text for the maps on the base layer to read as "Streets" and "Satellite" to look like the following:

// Create a base layer that holds both maps.
let baseMaps = {
  "Streets": streets,
  "Satellite": satelliteStreets
};
Change the center of our map to the geographic center of the United States using the coordinates [39.5, -98.5], with a zoom level of 3 and default layer streets. Our logicStep1.js file should look like the following:

The logic.js file shows the necessary edits for the earthquake map
styles.

Add the USGS URL for earthquake data by following these steps:

From the USGS home page (Links to an external site.) click the Earthquakes (Links to an external site.) link:

USGS Home page

Next, click the Real-time Notifications, Feeds, and Web Services (Links to an external site.) link:

Real-time Notifications, Feeds, and Web Services

Scroll down until you see "GeoJSON Summary Feed".

Click the GeoJSON Summary Feed (Links to an external site.) link:GeoJSON Summary
Feeds

On the right-hand side, click the All Earthquakes link under the "Past 7 Days" heading:

Click on the All Earthquakes link under "Past 7
Days."

Nice work! The GeoJSON data will launch in your browser:

The summary shows the recorded earthquakes for the past 7
days.



If we look closer at the geometry object, we'll see an additional data point in the coordinates object, 3.91, which is the depth of the earthquake in kilometers:

View the type of geometry and
coordinates.

NOTE
For more information on earthquake depth and other terms, see the Event Terms (Links to an external site.).

Copy the URL for the earthquake JSON data recorded for the past seven days, and add it in place of the previous URL in the d3.json() method. It should look like the following:

// Retrieve the earthquake GeoJSON data.
d3.json("https://earthquake.usgs.gov/earthquakes/feed/v1.0/summary/all_week.geojson").then(function(data) {
  // Creating a GeoJSON layer with the retrieved data.
  L.geoJson(data).addTo(map);
});
After saving the logicStep1.js file and opening the index.html file in your browser, the map should look like the following. Make sure you are referring to the correct logic file in your index.html file:

The Streets map with the markers for the earthquakes for the past
7-days.

Great job adding the earthquake data to our maps!

ADD/COMMIT/PUSH
Add, commit, and push your changes to your Earthquakes_past7days branch.

Let's make this data visually interesting by changing the marker to a circle with a radius representing the earthquake's magnitude, and then we'll style each earthquake data point.

# 13.6.2
Add Style to the Earthquake Data
As a first step in making the earthquake data more visually appealing, Sadhana would like you to add some styling to the earthquake data and vary the radius of each earthquake based on the magnitude.
After styling and modifying the radius of the circle for each earthquake's magnitude, our map should look similar to the following map:

The Street map marks each recorded earthquake with a light-orange
circle and a diameter representing the earthquake's
magnitude.

Before we write the code to create this map, make a copy of the logicStep1.js file and name it logicStep2.js. Now let's edit the file.

First, we'll change the basic marker to a circleMarker by using the pointToLayer function.

REWIND
For the pointToLayer callback function, the basic syntax for adding functionality to a marker is:

L.geoJson(data, {
pointToLayer: function(feature, latlng) {
return L.marker(latlng);
}
});
For our purposes, we'll use circleMarker instead of marker in the above code. Edit your GeoJSON layer code to look like the following:

// Creating a GeoJSON layer with the retrieved data.
  L.geoJson(data, {

// We turn each feature into a circleMarker on the map.

pointToLayer: function(feature, latlng) {
            console.log(data);
            return L.circleMarker(latlng);
        },
    }).addTo(map);
});
Save the file and let's see what the data looks like on the map. The index.html file should look like the following:

The Street map marks the recorded earthquakes with a
circle.

Next, we'll create a style for each earthquake by adjusting the line color, fill color, opacity, fill opacity, stroke, weight, and radius.

REWIND
When we defined the line style for the nonstop flight routes from Toronto, we created a style variable like the following:

let myStyle = {
color: "#ffffa1",
weight: 2
}
We'll create a function styleInfo(), which will contain all the style parameters for each earthquake plotted. Within this function, we'll create a getRadius() function to calculate the radius for each earthquake.

Add the following function styleInfo() inside the d3.json() method:

// This function returns the style data for each of the earthquakes we plot on
// the map. We pass the magnitude of the earthquake into a function
// to calculate the radius.
function styleInfo(feature) {
  return {
    opacity: 1,
    fillOpacity: 1,
    fillColor: "#ffae42",
    color: "#000000",
    radius: getRadius(),
    stroke: true,
    weight: 0.5
  };
}
Let's review the style we're creating for each earthquake:

In the styleInfo() function, we passed the argument feature to reference each object's features.
The opacity and fillOpacity are set at 1, the stroke is "true," and the weight is 0.5.
The fillColor is light orange, and the color is "#000000" (black).
The getRadius() function retrieves the earthquake's magnitude. Next, we'll create the getRadius() function to calculate the radius of the circle from the magnitude.


In the getRadius() function for our styleInfo() function, add the following code to retrieve the earthquake's magnitude: feature.properties.mag.

Next, we'll create the getRadius() function. Add the following code below the styleInfo() function:

// This function determines the radius of the earthquake marker based on its magnitude.
// Earthquakes with a magnitude of 0 will be plotted with a radius of 1.
function getRadius(magnitude) {
  if (magnitude === 0) {
    return 1;
  }
  return magnitude * 4;
}
In the getRadius() function, we'll pass the magnitude argument that will reference the feature.properties.mag in the styleInfo() function. Then we'll use a conditional statement that sets the magnitude to 1 if the magnitude of the earthquake in the JSON file is 0 so that the earthquake is plotted on the map. If the magnitude is greater than 0, then the magnitude is multiplied by 4.

Now, that we created our style, let's add it to the map.



To add style to the L.geoJson() layer, the style key will be assigned to the styleInfo function we created. Make sure the code for your L.geoJson() layer looks like the following:

// Creating a GeoJSON layer with the retrieved data.
  L.geoJson(data, {

// We turn each feature into a circleMarker on the map.

pointToLayer: function(feature, latlng) {
            console.log(data);
            return L.circleMarker(latlng);
        },
      // We set the style for each circleMarker using our styleInfo function.
    style: styleInfo
    }).addTo(map);
});
When you save your logicStep2.js file and open  index.html in your browser, your map will look like the following:

The Street map marks each recorded earthquake with a light-orange
circle and diameter representing the earthquake's
magnitude.

Great job styling each earthquake on our map!

ADD/COMMIT/PUSH
Add, commit, and push your changes to your Earthquakes_past7days branch.

Let's continue making the earthquake data visually appealing by styling colors to represent magnitudes as well as by adding informational popups.

# 13.6.3
Add Color and a Popup for Each Earthquake
Sadhana thinks that the size of the earthquake data based on magnitude looks great, but it's hard to tell the difference between earthquakes within the same area. As you toss around ideas to make this data more accessible to the viewer, you come up with the idea to color-code the earthquakes based on magnitude. You aren't quite sure how to do this yet, but you know that it should be possible based on your experience with JavaScript thus far. Basil loves the idea, so you get back to coding to figure out how to make it happen. And while you're working on changing the color code for magnitude, Basil and Sadhana suggest that you add the magnitude and location as a popup for each earthquake.
After we're done adding a color range for the magnitude and a popup for each earthquake, our map should look like the following:

The Street map marks each recorded earthquake with a circle and
diameter in a color representing a different magnitude. Popups show
magnitude and location for each
earthquake.

Before we write the code to create this map, make a copy of the logicStep2.js file and name it logicStep3.js. Now let's edit the file.

First, we'll create a fill-color range for the magnitude. In the styleInfo() function, our fillColor was set with fillColor: "#ffae42". We'll replace the hexadecimal color code with the function getColor(). Inside the parentheses, we'll add the dot notation code to get the magnitude as we did for the getRadius() function, since we'll change the color of each earthquake marker based on the magnitude.

Add the getColor(feature.properties.mag) function for the fillColorso that our styleInfo() function looks like the following:

// This function returns the style data for each of the earthquakes we plot on
// the map. We pass the magnitude of the earthquake into two separate functions
// to calculate the color and radius.
function styleInfo(feature) {
  return {
    opacity: 1,
    fillOpacity: 1,
    fillColor: getColor(feature.properties.mag),
    color: "#000000",
    radius: getRadius(feature.properties.mag),
    stroke: true,
    weight: 0.5
  };
}
Now we need to write code for the getColor() function to change the marker's color based on the magnitude. For example, if the magnitude is greater than 5, it will be a certain color, if the magnitude is greater than 4, it will be a different color, and so on.



For the getColor() function, we'll write a conditional expression with logical operators for the magnitudes. Add the following getColor() function below the styleInfo() function and above the getRadius() function. Sadhana suggests using the following colors for the magnitudes since they'll be visible on the Satellite map:

// This function determines the color of the circle based on the magnitude of the earthquake.
function getColor(magnitude) {
  if (magnitude > 5) {
    return "#ea2c2c";
  }
  if (magnitude > 4) {
    return "#ea822c";
  }
  if (magnitude > 3) {
    return "#ee9c00";
  }
  if (magnitude > 2) {
    return "#eecc00";
  }
  if (magnitude > 1) {
    return "#d4ee00";
  }
  return "#98ee00";
}
Let's save our logicStep3.js file and open the index.html file in the browser to confirm our code is working. When we select the dark map, our map should look similar to the following map:

The dark Satellite map marks each recorded earthquake with a circle
diameter and color representing different
magnitudes.

Now we need to edit the GeoJSON layer code to add the popup for the magnitude and location.



In the geoJson layer, we'll add the onEachFeature function to add a popup for each circle marker. Edit the L.geoJson() layer code to include the onEachFeature function with the bindPopup() method:

// Creating a GeoJSON layer with the retrieved data.
L.geoJson(data, {
    // We turn each feature into a circleMarker on the map.
    pointToLayer: function(feature, latlng) {
        console.log(data);
        return L.circleMarker(latlng);
      },
    // We set the style for each circleMarker using our styleInfo function.
  style: styleInfo,
    // We create a popup for each circleMarker to display the magnitude and
    //  location of the earthquake after the marker has been created and styled.
    onEachFeature: function(feature, layer) {
    layer.bindPopup("Magnitude: " + feature.properties.mag + "<br>Location: " + feature.properties.place);
  }
}).addTo(map);
When you save the logicStep3.js file and open your index.html file in your browser, the Satellite map option will look like the following:

The dark Satellite map marks each recorded earthquake with a circle
diameter and color representing different magnitudes. Popups show the
magnitude and location for each
earthquake

Great job on adding color and a popup marker to each earthquake!

ADD/COMMIT/PUSH
Add, commit, and push your changes to your Earthquakes_past7days branch.

Next, Sadhana will show you how to add the earthquake data as an overlay to the tile layer so that the data can be turned on and off by the viewer. 