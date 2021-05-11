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

# 13.2.4
Create a Simple Map
Now that you have added stylesheet links to your HTML page and CSS file, Sadhana will help you add the last two files you'll need to create a simple map—the config.js file for your API token and the logic.js file for your JavaScript and Leaflet code.
To create a map, we'll need to add two final pieces to our Simple_Map folder:

The config.js file, which will hold our Mapbox API key.
The logic.js file, which will contain all the JavaScript and Leaflet code to create the map and add data to the map.
Add the config.js File
In our Simple_Map folder, add a new folder in the static folder called "js." In the js folder, create a new file and name it config.js. This file will hold our Mapbox API key.

REWIND
The config.js file is like the config.pyfile we used to hold the OpenWeatherMap API and Google API keys.

On the first line of the config.js file, add the following code:

// API key
const API_KEY = "";
Add your Mapbox API key between the quotations and save the file.

Add the logic.js File
Next, in the js folder, create a new file and name it, logic.js. Now we'll add some boilerplate code to the logic.js file. Most of this code can be reused for many of the maps we'll create later on in this module.

On the first line, add the following code:

// Add console.log to check to see if our code is working.
console.log("working");
The console.log() function with the phrase "working" inside the parentheses will help us confirm that our logic.js file is being accessed in the console on Chrome.

Add a Map Object
Next, we'll add the map object, as shown on the Leaflet Quick Start Guide page with some slight modifications. We'll change the geographical center of the map to the approximate geographical center of the United States.

// Create the map object with a center and zoom level.
let map = L.map('mapid').setView([40.7, -94.5], 4);
In the code block above:

We're assigning the variable map to the object L.map(), and we'll instantiate the object with the given string 'mapid'.
The mapid will reference the id tag in our <div> element on the index.html file.
The setView() method sets the view of the map with a geographical center, where the first coordinate is latitude (40.7) and the second is longitude (-94.5). We set the zoom level of "4" on a scale 0–18.
An alternative to using the setView() method is to modify each attribute in the map object using the curly braces notation as follows:

// Create the map object with a center and zoom level.
let map = L.map("mapid", {
  center: [
    40.7, -94.5
  ],
  zoom: 4
});
This method is useful when we need to add multiple tile layers, or a background image of our map(s), which we will do later in this module.

Add a Tile Layer for Our Map
Now, we will add the map tile layer method to the logic.js file. The tile layer is used to load and display a tile layer on the map. We have two options to create a tile layer.

Use the Leaflet Documentation
The Leaflet Quick Start Guide (Links to an external site.) provides the tileLayer() code:

The Leaflet Quick Start Guide provides the tile layer
code.

We can copy this tile layer code and assign it to the streets variable, since the tile layer will create a street-level map. Add the following code block to your logic.js file:

// We create the tile layer that will be the background of our map.
let streets = L.tileLayer('https://api.mapbox.com/styles/v1/{id}/tiles/{z}/{x}/{y}?access_token={accessToken}', {
    attribution: 'Map data &copy; <a href="https://www.openstreetmap.org/">OpenStreetMap</a> contributors, <a href="https://creativecommons.org/licenses/by-sa/2.0/">CC-BY-SA</a>, Imagery © <a href="https://www.mapbox.com/">Mapbox</a>',
    maxZoom: 18,
    id: 'mapbox/streets-v11',
    tileSize: 512,
    zoomOffset: -1,
    accessToken: API_KEY
});
// Then we add our 'graymap' tile layer to the map.
streets.addTo(map);
Let's break down what's happening in this code block:

We assign the tileLayer() method, as shown in the Quick Start Guide's "Setting up the map" section to the variable streets. Leaflet doesn't provide a tile layer. Instead, it offers various tile layer APIs.
The following URLs appear in the parentheses of our tileLayer() method:
The API URL with a reference to the accessToken
The OpenStreetMap URL inside the curly braces of our tileLayer() method
We add the maxZoom attribute and assign it a value of 18.
We add the id attribute and assign it mapbox/streets-v11, which will show the streets on the map.
We add the accessToken attribute and assign it the value of our API_KEY.
Finally, we call the addTo() function with our map object, map on our graymap object tile layer. The addTo() function will add the graymap object tile layer to our let map.
To change the map's style, change the map id using the list of Mapbox ids below:

mapbox/streets-v11
mapbox/outdoors-v11
mapbox/light-v10
mapbox/dark-v10
mapbox/satellite-v9
mapbox/satellite-streets-v11
Use the Mapbox Styles API
To use the Mapbox Styles API, edit the URL in the Leaflet tilelayer()method, as detailed on the Leaflet website:

First, navigate to the Mapbox Glossary (Links to an external site.).

Search the Static Tiles API (Links to an external site.).

The Mapbox Glossary describes the Static Tiles API and lists related resources.

Copy this part of the URL: https://api.mapbox.com/styles/v1/mapbox/streets-v11/tiles/.

In your tileLayer() code, replace this part of the URL, https://api.tiles.mapbox.com/v4/{id}/, with the Mapbox Styles API URL you copied.

Remove the .png from the URL.

Remove the id attribute and the map style reference.

The code for the tileLayer() should look like the following:

// We create the tile layer that will be the background of our map.
let streets = L.tileLayer('https://api.mapbox.com/styles/v1/mapbox/streets-v11/tiles/{z}/{x}/{y}?access_token={accessToken}', {
attribution: 'Map data © <a href="https://www.openstreetmap.org/">OpenStreetMap</a> contributors, <a href="https://creativecommons.org/licenses/by-sa/2.0/">CC-BY-SA</a>, Imagery (c) <a href="https://www.mapbox.com/">Mapbox</a>',
    maxZoom: 18,
    accessToken: API_KEY
});

// Then we add our 'graymap' tile layer to the map.
streets.addTo(map);
NOTE
If you have trouble editing the URL, copy the URL above.

To change your map style, click on the Static Tiles API documentation (Links to an external site.) link on the Static Tiles API page.The Mapbox Glossary describes the Static Tiles API and lists
related
resources.

On the left sidebar, click on the Styles (Links to an external site.) link.

The API documentation page describes restrictions and
limits.

Below the Styles subheading, find a list of different Mapbox styles.Mapbox offers 10 style APIs for accounts with valid access
tokens.

To change the map style, use the style given in the URLs (e.g., "streets-v11," "dark-v10," etc.).

NOTE
For the rest of this module, we'll use the Static Tiles API format in the Leaflet tileLayer() method.

After adding all of the code, your logic.js file should look like the following:

Add the tile layer code to the logic.js
file.

Next, we'll add the logic.js and config.js scripts to the HTML page.

Add JavaScript Tags to HTML Page
The last step is to allow our index.html file to use the logic.js and config.js scripts. To do this, open up the index.html file and add the following <script> elements below the Leaflet JavaScript link script and above the closing </body> element, and save the file.

<!-- API key -->
<script type="text/javascript" src="static/js/config.js"></script>
<!-- Our JavaScript -->
<script type="text/javascript" src="static/js/logic.js"></script>
Your index.html file should look like the following after adding all the elements to the head and body sections:

Add all the elements to the index.html's head and body sections.

Open the Map in the Browser
Now, open the index.html file.

REWIND
To open the index.html file in the browser:

Open the command line and navigate to your Mapping_Earthquakes folder. The index.html file should be in the top-level of that folder.
On the command line, type python -m http.server and press Enter.
The basic map should look like the following in your web browser:

Your web browser will launch a basic open street map of North
America.

Congratulations on creating your first map using Leaflet and the Mapbox API!

NOTE
For more information, see the Leaflet documentation on methods using the map object and tile layer (Links to an external site.).

# 13.3.1
Add, Commit, and Push to a Branch
Basil wants you to commit your changes to the Simple_Leaflet_Map branch so the team can review. If he says there are no changes to be made to your branch, then you can merge it with the main branch.
Watch the following video to learn more about Git Branching.





First, we'll check to see if you're in the Simple_Leaflet_Map branch. In the command line, navigate to your Mapping_Earthquakes folder and type git branch. If the following output is returned with an asterisk next to the branch name, you're in the Simple_Leaflet_Map branch:

* Simple_Leaflet_Map
  main
Just as we have checked the main branch status of other repositories, we'll do the same with the Simple_Leaflet_Map branch.



After typing git status, the command line should show the following:

Type git status to show the status of the Simple_Leaflet_Map
branch.

To see all the folders and files in the Simple_Map folder, type git status -u and press Enter. The output in the command line should look like the following:

Type git status - u to show the status of the Simple_Leaflet_Map
branch.

REWIND
We don't want to add config.js file to the repo because our repository is public. This means the Mapbox API key would be available for anyone to copy and use, possibly causing us to incur charges.



If you didn't initialize the repository with a .gitignore file, we'll create one. Then we'll add config.js to the .gitignore file so that GitHub doesn't track that file.

In VS Code, create a new file in the Simple_Map folder and name it .gitignore. Your repository folder should look like the following:

Use VS Code to create a .gitignore file and add it to the
Mapping_Earthquakes
folder.

Next, add the following lines to the .gitignore file and save the file:

# Ignore the config.js file.
config.js
In the command line, type git status - u and press Enter. The output should have the .gitignore file and all the files as before, except the config.js file. All the files in red will be tracked when we use git add, with the exception of the config.js file. 

After creating the .gitignore file, type git status -u for the status
of the Simple_Leaflet_Map
branch.

Next, we'll add these folders and files to the Simple_Leaflet_Map branch as we did for the main branch.



After typing git push and pressing Enter, the output message will look like the following:

Type git push and press enter for output instructions on how to set an
upstream branch for
Simple_Leaflet_Map.

To push the folders and files to the Simple_Leaflet_Map branch for the first time, type git push --set-upstream origin Simple_Leaflet_Map in the command line and press Enter.

NOTE
To add any files after this initial push, type git push.

Now all the folders and files are in the Mapping_Earthquakes repository in the Simple_Leaflet_Map branch. Confirm this by navigating to the repository and refreshing the page.

We can see that we have created a new branch, indicated at the top. If we click the dropdown menu "Branch: main" in our repository, the Simple_Leaflet_Map branch appears.

Confirm the Simple_Leaflet_Map branch at the top of the webpage and in
the dropdown
menu.

To check if our folders and files are in the Simple_Leaflet_Map branch, select the branch from the dropdown menu. You should see all the files we added.

Confirm the folders and files are in the Simple_Leaflet_Map branch
from the dropdown
menu.

Congratulations on adding your files to a new branch!

# 13.3.2
Compare Branch to the main Branch
Basil has reviewed your code and is impressed with the comments you made; comments to your code allow others to understand what the code does.  Now that your code has Basil's approval, Sadhana will walk you through the steps to merge your branch with the main branch. The first step when merging a branch is to compare the changes between the Simple_Leaflet_Map branch and the main branch.
To merge your Simple_Leaflet_Map branch with the main branch, we will:

Compare the changes between the Simple_Leaflet_Map branch and the main branch so that we can merge them.
If we are able to merge the Simple_Leaflet_Map branch into the main branch, we need to create a pull request on GitHub.
After we review the pull request, we can merge the branch into the main branch.
Let's compare the changes between our Simple_Leaflet_Map branch and the main branch:

Navigate to your Mapping_Earthquake GitHub repository.

To start merging your branch into the main branch, compare the branches to confirm they can be merged.

NOTE
If changes have been made in the main branch after you added your files to a branch, you might not be able to merge.

You have two ways to compare your branch with the main branch:

Click the green "Compare & pull request" button, or
Click the gray "New pull request" button.
(If you click the "Compare & pull request" button, skip to Step 5.)

There are two ways to create a pull request to compare the
branches before merging
them.

If you click the "New pull request" button, a new page will open with two buttons: "base: main" and "compare: main." Compare the Simple_Leaflet_Map branch with the base or main branch.

NOTE
Developers and team members often refer to pull requests as "PRs."

The Compare changes page has two buttons: "base: main" and
"compare:
main."

Click on the "compare: main" button and select the branch you want to compare (the Simple_Leaflet_Map branch).

Click the "compare: main" button to select the branch for
comparison.

Next, Sadhana will show you how to create a pull request required to merge a branch with the main branch.

# 3.3.3
Create a Pull Request
You made it through the first step. Now, Sadhana will show you how to create a pull request. This step is important when working on a team because it allows other team members to check your code on your branch, and then either ask you to make changes or approve it so it can be merged with the main branch.
The next step is to create a pull request on GitHub. This step is essential when working with your Disaster Reporting Network team. It will allow Basil and Sadhana to review and run your code to verify there are no errors. If there are errors in your code, or if the code can be modified to be easier to read, then they will ask you to make changes. If your code looks good and there are no changes to be made, then you can merge your branch with the main branch.

Let's walk through the process of creating a pull request. First, select the Simple_Leaflet_Map branch.

Click the "compare: main" button to select the branch for
comparison.

Or, you can select the green "Compare & pull request" button.

Click the "Compare & pull request"
button.

A new page called "Open a pull request" will launch.

When you open a pull request, there are five key elements, as
described in the main
text.

The page shows the five key elements of a pull request:

Near the top of the page is a green checkmark and text stating "Able to merge." If you're unable to merge, GitHub will display an explanatory message.
Next is the commit message you made.
"Reviewers" and "Assignees" are members, such as yourself, with access to the repository. You can assign the pull request to yourself. Labels, Projects, and Milestones are completed by team members and owners of the repository. Click on a gear wheel to modify any of these items.
In the "Leave a comment" field, describe what you're adding to the main branch in the pull request.
After entering a comment, click the green "Create pull request" button.
Scroll below "Open a pull request" to see the files you're adding to the pull request.

The file to be merged with the main branch appears below "Open a
pull
request."

Write a message and create a pull request. In the "Leave a comment" field, type the following message:

Adding the following folders and files to create a simple Leaflet map.
- .gitignore
- Simple_Map/index.html
- Simple_Map/static/css/style.css
- Simple_Map/static/js/logic.js
After you click the green "Create pull request" button, the page should look similar to the following:

The "Merge pull request" page includes your comment and any
conversation, commits, checks, and files
changed.

Reviewers can add a comment in the "Leave a comment" field. For example, Sadhana or Basil could type approval and further instructions: "Looks good to me. You can merge." Once a reviewer approves your pull request in a comment, you can click the green Merge pull request button.

If your code looks good, click the "Merge pull request" button.

Don't navigate away from GitHub. Next, Sadhana will walk you through the final steps of merging your branch with the main branch.

# 13.3.4
Merge Branch Into main Branch
Congratulations on creating a pull request, which can be daunting sometimes. The final step will be to merge the Simple_Leaflet_Map branch into the main branch.
The following video walks you through the process of merging a branch into the main branch.



After clicking the "Merge pull request" button, the page will refresh with two options: "Confirm merge" or "Cancel."

Either confirm or cancel the merge by selecting the appropriate
button.

Click the green "Confirm merge" button. The page refreshes to confirm, in three places, that the pull request has been merged into the main branch.

The page confirms, in three places, a successful
merge.

This page gives the option of deleting the branch. However, don't delete it so that future interns can use it to create a simple Leaflet map.

The page gives the option to delete the branch after the successful
merge.

Navigate to the main branch on GitHub to confirm all the folders and files have been merged from the Simple_Leaflet_Map branch.

The folders and files appear on the GitHub homepage after the
successful
merge.

We are almost done!

Next, pull the latest changes on the main branch on our computer because the main branch on our computer is not up to date. Follow these steps.

Open the terminal or Git Bash and type git checkout main and press Enter.

Type git status and press Enter. The output might tell you that you are up to date, which can be misleading, or it might say you are "1" commit behind the Simple_Leaflet_Map branch.

Type git pull and press Enter. The output should look like the following:

Use git pull to see the changes applied to your
Mapping_Earthquakes
folder.

To confirm that the files are in the main branch on your computer, if you have a Mac type open . to view the directory in Finder, or if you have a PC type start . to view the directory in File Explorer.

Congratulations on merging your Simple_Leaflet_Map branch into the main branch!