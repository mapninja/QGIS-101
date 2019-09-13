# QGIS in 60 Minutes

# Overview  

This workshop will introduce participants to QGIS, a free and open source desktop GIS application, comparable and competetive in many way with Esri's ArcGIS Desktop. We will focus on a very basic introduction to the QGIS interface, and common data carpentry tasks that will come in handy as you prepare and create vector data, in particular, for use in Google Earth Engine. 

# Setup

Users should prepare for this workshop by installing the QGIS software appropriate for their operating system and downloading the data to their local hard drive.

## Software

This workshop was created using QGIS version 3.4, which is the long-term release. If you are in new user we suggest installing the latest long-term release for your operating system. While the latest beta release contains extra features and functionality, it often and also contains bugs and limited functionality, which can be frustrating to new users.

To download QGIS for your operating system go to QGIS.org and click on the download link.

[https://qgis.org/en/site/forusers/download.html](https://qgis.org/en/site/forusers/download.html)

## Data

The data package for the workshop can be downloaded from [https://github.com/StanfordGeospatialCenter/QGIS-in-60/archive/master.zip](https://github.com/StanfordGeospatialCenter/QGIS-in-60/archive/master.zip)

The project data folder contains the following datasets:

* **deathAddresses.csv**  - this is a table latitude and longitude coordinates for addresses affected by the cholera outbreak. This table also contains the number of deaths at each address.  
* **John_Snow_Map.tif** - this is a georeferenced image of the map from John Snow's original report on the cholera outbreak of 1854. 
* **Study_Area.shp,.dbf,.prj, etc...** - This is a shapefile, and is simply a rectangular feature that describes our area of interest.  *Note that a shapefile is not actually a file, but a set of files, most of which are critical to the proper function of the dataset. All of these files must remain adjacent, and with the same name, as the other components of the shapefile.* 
* **Water_Pumps.geojson** - this is a spatial data file containing the locations of all of the water pumps recorded in John Snow's original map of the cholera outbreak. We'll actually create a version of this, ourselves, but I have included this, just in case. 


## Let's go!
# Getting started on a project (10 minutes)

In this section we will cover starting a new QGIS project. We will create a new map document, go over the basic QGIS interface, customize that interface, add a plug-in and bring a base map into your QGIS project.

### Create a Map Document

1. To create a new map document, simply open QGIS and save the resulting empty document to the top level of your project folder, naming your new document something meaningful like "SnowMap.qgz" or "Cholera_Map.qgz"

*Notice that when you save your map document a new folder in your data browser panel appears. This folder is called Project Home and is a shortcut to the folder containing your map document. It's always a good idea to save your map document to a high-level folder above your data and other project directories.*

# Interface overview

The QGIS interface is similar to many desktop GIS applications. The basic you GIS interface resembles most others GIS interfaces in that it uses a table of contents and data frame model for user interaction. In QGIS the **Table Of Contents** is referred to as the **Layers Panel** and the **Data Frame** is referred to as the **Map Canvas**.

## The Basic Components of the QGIS Interface

The QGIS interface is made up of three basic components:

**The Map Canvas** – the map canvas is where your visualizations of data will show up when you had a new data layer. This is where you will view the changes that are made when you adjust symbology, when you change the order of layers, or when you produce a new data set through geo-processing  

**Tabbed Windows:**

* **The Browser Window** – Functions much as Explorer does in Windows. In this window, you can visualize your drives and folders. Is the equivalent of ArcCatalog in ArcMap.
* **The Layers Window** – This is where your added geographic and non-geographic datasets will show. This is similar to the Table of Contents in ArcMap.
* **Other Panels** - there are many other panels that it is possible to enable in the QGIS interface. We will be making use of the **Processing Toolbox** and **Layer Styling** panel for this workshop.

**General Toolbars:**

* **File Bar** – Has the basic commands of any file: New, Open, Save, Save As. The New Print Composer and Composer Manager are to create and manage layout views.
* **Map Navigation** – Allows the user to Pan, Zoom to a Selected Feature, Zoom In, Zoom Out, Zoom to previous/next extent, and Refresh.
* **Attributes** – These tools allow the user to: Identify attributes, Select / Deselect features, Opens attribute table, measure distance/areas/angles, create spatial bookmarks.
* **Plugins** – QGIS comes with two default plugins: Python Console and QGis 2 Leaflet Webmap.
* **Help** – The question mark booklet is linked to the QGIS User Guide.
* **Manage Layers** – This bar is to add layers (vector, raster, new shapefile layer)

# Customize the interface

When you first open QGIS, you might find the toolbars and panels that are enabled by default are more than your project calls for. Most panels and toolbars in the QGIS interface can be moved around by grabbing the title bar of panels, or the dotted handle on toolbars, and dragging them to the desired location in the interface. You can also use the View menu to turn panels and toobars on and off.

![](./media/customize.gif)

1. Toggle the visibility and move toolbars and panels until your QGIS interface resembles the image below.

![](./media/customize.png)

# Add a plugin
The first thing we would like to do is add a base map layer to our map project. We will use the **Quick Map Services** plug-in to add a base map created by [Stamen design](https://stamen.com/). QGIS uses a plug-in model to extend the functionality of the basic software. Most plug-ins are contributed by members of the QGIS community and many extend functionality by adding interactivity with external services like geocoding, routing, and base map services.

1. On the **Main menu** of **QGIS**, find the **Plug-ins** menu and open the **Manage and install plugins** dialogue.  
2. In the search box at the top of the dialogue, search for the term "**QuickMapServices**"    
3. The search should return a plug-in called "**QuickMapServices**." 
4. Click on the **QuickMapServices** plug-in name and then click the install plug-in button
5. Once the plug-in has successfully installed, Close the plug-in management dialog.

![](./media/pluginMenu.png)  

# Add a basemap service layer

1. Installing the **QuickMapServices** plug-in should have added a new menu item to the **QGIS Main Menu** called "Web".
2. Click on the Web menu and from the **QuickMapServices** item select "**Settings**."
3. Select the "**More Services**" tab and click on the "**Get contributed pack**" button. This will download a large list of web map services that can be used directly into GIS as base maps.  
![](./media/contribpack.png)  
4. Once the contributed pack has been downloaded click **Save** to close the dialog.
5. Now return to the quick map services menu, and select the **Stamen> Stamen Toner Lite** base map.
6. **Save** your **map document**.

![](./media/stamenbasemap.png)

# Add an existing data layer
Now we're going to add an existing data layer. The data layer that we will add describes our **Area Of Interest** in this study. This layer will provide us with a convenient way to orient our data frame to the area that we are interested in, as well as providing a way to limit the processing extent of certain geo-processing tools.

1. In the **QGIS Browser panel**, find the data folder for this workshop (Hint: look for the "**Project Home**" folder) and double-click on the **study_area.shp** file, to add it to your **map project**.
2. In the **Layers panel**, right-click on the **study_area layer** and select "**Zoom to layer**."
3. On the **Main menu**, enable the **Layer styling panel** from the **View>Panels menu**. 
4. In the **Layer styling panel** select **Simple fill** from the panel at the top, and change the **Fill style** to "**No brush**." If you would like you can also change the **Stroke color** & **Stroke width** of the stroke to make it more visible against the black-and-white basemap.
5. **Save** your **map document**.

![](./media/studyareaadd.png)

# Explore navigation tools

Now we will explore the **basic navigation tools** in QGIS. These are the tools that you will 

The **Map Navigation Toolbar** provides the bulk of the tools for navigation in
the **Map Canvas**. Most of them are fairly obvious. Take a moment to explore
each of these tools, and how it works.

![](./media/image13.png)  The **Touch Zoom and Pan** - Works if you have a notebook with touch screen.
Zoom in and zoom out using double finger touch.

![](./media/image14.png)  The **Pan Map** changes the Extent of Map Canvas, without changing the scale.
Click on the Pan Tool and use it to move around the Map Canvas.

![](./media/image15.png)  The **Pan Map to Selection** changes the Extent of your Map Canvas to the
feature being selected, without changing the scale

![](./media/image16.png)  The **Zoom In Tool** and  ![](./media/image17.png)  **Zoom Out** works exactly as you would expect. Click on the Zoom Tool, and drag
a box to enclose the Continental United States. You can also single-click with
this tool to use it as a Fixed Zoom Tools.

![](./media/image18.png)  The **Zoom Full** zooms you to the full extent of the layer in your Map Project with the largest spatial extent. This can sometimes be problematic if you are
working at a local level, but using one or more layers that are global in extent
(for example, many of the network base map services).

![](media/image19.png)  The **Zoom to Selection** changes the Extent of your Map Canvas and zooms in or
out to the selected feature.  

----

## *Explanation: A Sense of Scale*

When zooming in or out, the **Scale Values** at the bottom page changes. Remember that the bigger the number (**1:60,000,000**), the larger the area being displayed. Although **60,000,000** is bigger than **60**, a scale **1:60,000,000** is a small scale and **1:60** is a large scale because the division of **1/60,000,000** is smaller than **1/60**.

![](./media/image20-drop-shadow.png)

![](./media/image22.png)  The **Zoom to Layer** to a specific layer extent.

![](./media/image23.png)  The **Zoom Last** and ![](./media/image24.png) **Zoom Next** works as a Redo or Undo tool **ONLY** for the Scale/Extent in your Map Canvas. This tool is particularly useful if you change your Map Extent inadvertently.

![](./media/image25.png)  The **Refresh Button** will reload your Map Extent


----

## *On Your Own Sidetrip: Spatial Bookmarks*

Often, we want to be able to move around in our data frame examining different parts of the map zooming in and out, and then returning to our primary area of interest. This can be easily accommodated through the use of spatial bookmarks. Here you'll create a spatial bookmark which allows us to quickly return to the area that we are interested in.

1. Previously we used the main menu to enable a panel. This time, try right-clicking in any empty area of the toolbar then scroll down and select the **Spatial Bookmarks panel** from the menu that is presented.
2. Right-click on your study_area layer and select **Zoom to layer**.
3. Click on the **Add Bookmark** button and rename the resulting Spatial Bookmark: "**SOHO**"  
![](./media/spatialbookmark.png)
4. Click on the **Zoom Full** button to zoom to the world, then use the **Zoom to bookmark ** button to return to your Area of Interest.  


----

# Working with CRS in QGIS
Here we will examine the default **Coordinate Reference System**, which should currently be sent to **Web Mercator** and we will change it to **Universal Transverse Mercator** to match our study area layer.  

#### Examine the CRS of a data layer
1. Right-click on the **study area** layer select the Layer Properties from the menu.
2. Click on the **Source** tab on the left side of the properties panel, and note in the section called **Geometry And Coordinate Reference System** that the CRS of this layer is:  

```EPSG:32630 WGS 84 / UTM zone 30N```  

![](./media/layercrs.png)
3. Click OK to close the **Layer Properties** Dialog  
4. On the **Main Menu** Open the **Project Properties** from the **Project** menu.  
5. Click on the **CRS** tab at the left and note that the project is in a projection called:  

```EPSG:3857 WGS 84 Pseudo-Mercator```   

*This is the projection of the basemap and is the default for the project because the basemap was the first layer that we added to the project.* 

![](./media/projectcrs.png)

## Change the Project CRS  
1. Locate the CRS of the **Study_Area** layer in the "**Recently used coordinate reference systems**" section, or type the EPSG code "**32630**" into the Filter box at the top of the **Properties** dialog.  
![](./media/newprojectcrs.png)
2. Click on the ```EPSG:32630 WGS 84 / UTM zone 30N``` and then click OK to change the CRS of the Project to the same as the layer **Study_Area**.
3. Save your changes by clicking on the Save button ![](./media/savebutton.png) on the Project toolbar.  

You should now see that the base map and study area layer in the map canvas have rotated slightly and are now oriented north-south.

# Working with data in QGIS

## Create a data layer from an XY table (10 Min)

Often the data sets that you want to work with will not come as spatial data sets. In this step we will add a table of data that contains fields with the latitude and longitude coordinates of the deaths addresses we want to analyze.

1. Click on the **Add Delimited Text Layer** button ![](./media/delimitedlayer.png)to open the Data Source Manager dialog.
2. For **File Name**, browse to the **data** folder and select the **deathAddresses.csv**
3. Set the remainder of the settings as follows, and click **Add & Close** to import the layer:    

| setting | value |
|--------------------------:|--------------------------------------------------------------------|
| File Format:  | CSV |
| Record and Field Options: | "First records has field names" = true "Detect field types" = true |
| Geometry Definition: | Point coordinates: "X field" = 'xcoord, "Y field" = 'ycoord' |
| Geometry CRS: | EPSG:4326 - WGS 84 |


![](./media/datasourcemanager.png)  

![](./media/addedpoints-drop-shadow.png)  

----

## *On Your Own Sidetrip: Layer symbology* 
Proportional symbols on Death Addresses

1. If not already, **click** on the **deathAddresses** layer to highlight it and focus the **Layer Styling panel** on this layer and use the following settings to adjust the **deathAddresses Symbology**: 

| setting | value |
|------------------:|--------------------------------|
| Symbology Type:  | Graduated |
| Column: | Num_Cases |
| Symbol: | *click to change the color if you like* |
| Legend Precision: | 1 |
| Method: | Size |
| Size from: | 10,50,'Map Units' |
| Classes>Mode: | Equal Interval |
| Classes: | 3 |

Because QGIS now features live update of symbology changes you should see these changes apply as you change the setting values.  

![](./media/deathsymbol-drop-shadow.png)

### *Bonus: Adding Drop Shadows*  
QGIS actually has a number of great cartographic and rendering features that are, frankly, more advanced that most other desktop GIS packages. One of those is the ability to use "**Adobe Photoshop/Illustrator**" type rendering techniques. Here is my favorite, and a great way to make a map '**pop**' a little. 

1. At the bottom of the Layer Styling panel, look for the "Draw Effects" option and check it, then click  on the star that becomes active.
2. Check  the option for Drop Shadow and adjust the settings to see what effect they have.

![](./media/dropshadowdeaths-drop-shadow.png)  

----

### Viewing the Attribute Table

Up to this point we've been mostly concerned with building a new map project. Now we'd like to take a peek at some of the data behind the Map Canvas.

1. Right-click on the **deathAddresses** layer in the **Layers** panel and select **Open Attribute Table**.
2. Note that you can sort fields, scroll, select by attributes, etc...

----

### *On Your Own Sidtrip: Statistics on a field*  

As mentioned, above, the **Num_Cases** field in the Death Addresses data indicates the number of deaths at each address in the dataset. You can get a simple statistical snapshot of the variable from the Attribute Table.

1. Close the Attribute Table
2. On the pull-down menu go to **Vector > Analysis Tools > Basic Statistics for Fields**
3. On the window select **Death Addresses** as the Input Vector layer and **Num_Cases** as the Target field.
4. **Click Run** and **Close** 
5. Look for the **Results Viewer** panel which should have been activated, and click on the **Hyperlink** to open the summary in a web browser.  
![](./media/resultsviewer-drop-shadow.png)   

----

# Creating spatial data

Perhaps one of the most useful features of QGIS is the ease with which you can convert spatial data, and create it from other reference layers (i.e. a georeferenced map like our John Snow cholera outbreak image). When working with historical data, you will often be working from scanned paper map resources. The techniques described, below, can as easily be used when working with satellite or aerial imagery. It's just a different reference layer. 

## Make an Empty Shapefile  

First, we need to add our reference layer, John Snow's map of the cholera outbreak of 1854:  

1. In the Browser Window, right-click on the John_Snow_Map.tif and **Add Selected Layer to the Canvas**.  

Now we will create a New Empty Shapefile, to hold the data that we will digitize from the John Snow Map:

2. On the **Main Menu**, go to **Layer>Create Layer** and select the **New Shapefile** option
3. Use the following settings:

| Setting | Value |
|-----------------------:|-----------------------------------|
| File name: | Save to /data/ as water_pumps.shp |
| File encoding: | system |
| Geometry type: | Point |
| Additional dimensions: | None |
| CRS: | EPSG:4326 - WGS 84 |

![](./media/newshapefile.png)

3. Add a New Field, add a **text  data** field called 'Label'
4. Click OK to create the empty shapefile and add it as a layer.

## Add points to your shapefile

1. Right-click on the water_pumps layer and select **Toggle Editing**
2. Click on the Add Point Feature button ![](./media/editpoint.png)and add a point for one of the Water Pumps in the John Snow map. 
3. Label the point with the street it is on (really, just pick the nearest one you can read) in the **Feature Attributes pop-up** and click ok to create the feature.  
![](./media/featureattributes.png)  
4. Continue digitizing Until you have captured all 12 water pumps in the map.
5. Right-click on the water_pumps layer and selelct **Toggle Editing** and save your edits when you are prompted.

----

### On Your Own Sidetrip: Labels

1. Click on the **water_pumps** layer to activate it in the **Layer Styling** panel
2. Click on the **Label** tab of the **Layer Styling** panel
3. Change the Label option to **Single labels**
4. Set **Label with:** to the 'label' field.
5. Increase the **Text Size** to **14**
6. Click on Buffer tab and enable the **Draw text buffer** option. 

![](./media/labels.png)  


# Exporting from QGIS
## ...and Importing to Google Earth Engine

Google Earth Engine currently only supports uploads of shapefiles through the GUI, but allows upload of CSV and Shapefile through the API. We'll just cover using the GUI with a shapefile, here, but you can find documentation on the process of getting a CSV into Google Earth Engine, here: [https://developers.google.com/earth-engine/importing#upload-a-csv-file](https://developers.google.com/earth-engine/importing#upload-a-csv-file)

## Export a Layer to Shapefile  

When we added the the Death Addresses data, at the beginning of th eworkshop, we did so as a CSV. Here, we will export this data to a shapefile, compress it into a .zip file and 




----

# Extra Credit: Time Permitting or On Your Own

## Basic spatial data analysis

### Voronoi (Thiessen) polygon (Spatial Allocation)

Thiessen polygons allocate space in an area of interest to a single feature per polygon. That is, within a Thiessen polygon, all other features are closer to the point that was used to generate that polygon than to any other point in the feature set. In this case, we will create a set of Thiessen polygons based upon the locations of the Water Pumps in our project. This will allow us to easily allocate all of the points in our death addresses dataset to the water pump that they are nearest using a simple spatial join.

1. On the Main Menu go to menu go to **Processing \> Toolbox**
2. Go to the **Processing Toolbox Window** and change the view from **Simplified Interface** to **Advanced Interface.**
3. Search for **Voronoi.**
4. **Double–click** the **Voronoi polygons** tool under **Grass commands.**
5. On the v.voronoi tool window input the select **Water Pumps** as the **Input points layer.**  
![](media/image004-drop-shadow.png)

6. On **Grass region, click the 3 dots** and select **Use layer/canvas extent.**
1.  On the **Select extent window,** scroll down to find **Study Area.**
2.  **Click OK**
3.  **Click the 3 dots** beside the Voronoi diagram option, and **select Save to file.**
4.  Browse to your Data folder and **save** the shapefile as **Voronoi.**
5.  **Click Run**  
![](media/image005-drop-shadow.png)

6. **Open** the Attribute Table of the **Voronoi** layer to explore how each Voronoi Polygon has the name of the pump enclosed.

### Spatial Join (Point Aggregation)

Now that you have created the Voronoi polygon layer, you will “allocate” each of the deaths to one of the Voronoi polygons. To do this, we will use the **Join Attributes by Location** tool. Conceptually, what we will be doing is like passing our points through the polygons so that the polygon's attributes "stick" to the points.  

![](media/spatialJoin.png)

1. On the pull-down menu go to menu go to **Vector \> Data Management Tools \> Join attributes by location**

1.  Select **Death Addresses** as the Target vector layer and
    **Water_Pump_Voronoi** as the Join vector layer.

2.  **Click Browse** to save the **Output GeoJSON** as **Deaths_Allocated** in
    your **Data** Folder.

3.  **Click OK**

4.  Click **Yes** to add the new layer to the TOC (Table of Contents) and Close
    the Join the attributes by location window.

5.  The resulting layer is added to the Map Canvas. **Open** its **attribute table** to confirm that the attributes of the Water Pumps have been transferred:  
![](media/joinedTable.png)

### Summary Statistics

Finally, we would like to summarize the deaths in the outbreak, grouping our summary by the name of the Water Pump that each Death Address is nearest. We will do this using the **Group Stats Tool** which allows us to do a statistical summary similar to the one we did earlier on the entire data set, but this time grouped by nearest water pump.


1.  On the pull-down menu go to **Plugins\> Manage and install plugins.**

2.  On the Plugins window search, type **Group Stats** and select it.

3.  Click on **Install plugin.**

4.  Close the **Plugin Window.**  
![](media/image007-drop-shadow.png)


After the installation a **GroupStats Tool** ![](media/image008.png) appears on the Vector Toolbar.

1. **Click** the **Group Stats tool**

2. **Select Deaths_Allocated** as Layer.  
![](media/image009-drop-shadow.png)

Drag from **Fields** to **Column**: average, count and sum. 

On **Rows,** drag Name (originally from the Water_Pump data layer), and 

on **Value** drag **Num_Cases.**

1.  **Click** on **Calculate** to visualize the summary table.

2.  **Click** the Sum field header on the resulting table to **Sort descending** on the **SUM\_Num\_Cases** field.

Note that the **Broadwick Pump** has the highest value for two of three
significant attributes: **Count** (No. of households), **Sum** (Total Deaths),
and **Average** (Mean Deaths per Household).

1.  On the **Group Stats Window,** go the **Data\> Save all to CSV file. Save** the **Ouput Table** to your **Data** Folder and name it **Deaths\_Summary\_by\_Pumps**.

2.  **Close** the Group Stats Window

## Basic Measures of Spatial Central Tendency

### Spatial Mean (Mean Center)

The Mean Center is the average x- and y-coordinate of all the features in the study area. It's useful for tracking changes in the distribution or for comparing the distributions of different types of features. Here, we will use the Mean Center to highlight the distribution of deaths around the Broad Street Pump.  

First, we will calculate a simple spatial mean. This is simply the mean center of the **distribution of locations** 

1. On the pull-down menu go to menu go to **Vector \> Analysis \> Mean
coordinate(s)**  
![](media/image010-drop-shadow.png)  

1. Select **Deaths_Allocated** as the Input vector layer.
2. Leave the **Weight field** and **Unique ID field** as **Optional.**
3. **Click Browse** to **save** the Output Shapefile as:
    **Deaths\_Spatial\_Mean** to the **Data** Folder**.**
4. **Click OK** to calculate the **Mean Center** and **Close**.
5. Change the **Symbology** for the **Deaths\_Spatial\_Mean layer** to something that contrasts with the other symbologies.

### Weighted Spatial Mean

1. **Run** the **Mean Center tool** again, this time assigning the
   **Num_Cases** field as the **Weight Field**.
2. **Save** the **Output Shapefile** to the **Data** folder and name it **Deaths_Weighted_Spatial_Mean**.
3. **Apply a symbology** to the **Deaths_Weighted_Spatial_Mean layer**.

#### Bonus:  
Set the "Unique ID" option to the "label" field and observe the results. This has the effect of "casing" the spatial mean, based upon the spatial allocation that we did earlier.

### Standard Distance

The Standrad Distance is the spatial statistics equivalent of the standard deviation. It describes the radius around the spatial mean (or weighted spatial mean), which contains 68% of locations in your dataset. It can be very useful for working with GPS data.

![](media/image011-drop-shadow.png)

On the pull-down menu go to menu go to **Processing \> Toolbox** to open the
**Processing Toolbox Window.**

![](media/image012-drop-shadow.png)

On the **Processing Toolbox Window type** to **search**: **Spatial point pattern
analysis** and **double click** to open the tool window.

1.  Select **Death Addresses** as the **Point** layer.

2.  Click the 3 dots and **Select** Save to a file.

3.  **Give** an appropriate name and **Save** the **3 Output Files** on your
    **Data** folder.

![](media/image013-drop-shadow.png)

**Click Run** to calculate the **Standard Distance, Mean Centre and Bounding
Box.**

>   The red dot is the mean center (no weight field; the large circle is the
>   standard distance, which gives an indication of how closely the points are
>   distributed around the mean center; and the rectangle is the bounding box,
>   describing the smallest possible rectangle which will still enclose all the
>   points.

