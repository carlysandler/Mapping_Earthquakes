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