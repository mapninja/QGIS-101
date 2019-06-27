# QGIS 101

## Overview

This workshop aims to accomplish two things: Introduce participants to basic vocabulary, concepts and techniques for working with spatial data in research and introduce the interface and tools in QGIS, a free & open source desktop GIS software

## Setup

```addcontent```

### Software

`Overview and Installation & Setup Guidance for the Packages covered will be presented here.`  

### Data

```update```

The data package for the workshop can be downloaded from <here>

* deathAddresses.csv  
* John_Snow_Map.tif
* Study_Area.shp
* Water_Pumps.geojson

## Getting started on a project  

In this section we will cover starting a new QGIS project. We will create a new map document, go over the basic QGIS interface, customize that interface, add a plug-in and bring a base map into your QGIS project.

```addcontent```

### Create a Map Document

```addcontent```

1. To create a new map document, simply open QGIS and save the resulting empty document to your project folder, naming your new document something meaningful like "SnowMap.qgz" or "Cholera_Map.qgz"

### Interface overview

The QGIS interface is similar to many desktop GIS applications. 

```addcontent```

#### The Basic Components of the QGIS Interface

The QGIS interface is made up of three basic components:

**The Map Canvas **– the map canvas is where your visualizations of data will show up when you had a new data layer. This is where you will view the changes that are made when you adjust symbology, when you change the order of layers, or when you produce a new data set through geo-processing  

**Tabbed Windows:**

* **The Browser Window** – Functions much as Explorer does in Windows. In this window, you can visualize your drives and folders. Is the equivalent of ArcCatalog in ArcMap.
* **The Layers Window** – This is where your added geographic and non-geographic datasets will show. This is similar to the Table of Contents in ArcMap.

**General Toolbars:**

* **File Bar** – Has the basic commands of any file: New, Open, Save, Save As. The New Print Composer and Composer Manager are to create and manage layout views.
* **Map Navigation** – Allows the user to Pan, Zoom to a Selected Feature, Zoom In, Zoom Out, Zoom to previous/next extent, and Refresh.
* **Attributes** – These tools allow the user to: Identify attributes, Select / Deselect features, Opens attribute table, measure distance/areas/angles, create spatial bookmarks.
* **Plugins** – QGIS comes with two default plugins: Python Console and QGis 2 Leaflet Webmap.
* **Help** – The question mark booklet is linked to the QGIS User Guide.
* **Manage Layers** – This bar is to add layers (vector, raster, new shapefile layer)

### Customize interface

When you first open QGIS, you might find the toolbars and panels that are neabled by default are more than your project calls for. Most panels and toolbars in the QGIS interface can be moved around by grabbing the title bar of panels, or the dotted handle on toolbars, and dragging them to the desired location in the interface. You can also use the View menu to turn panels and toobars on and off.

![](./media/customize.gif)

1. Toggle the visibility and move toolbars and panels until your QGIS interface resembles the image below.

![](./media/customize.png)

### Add a plugin
The first thing we would like to do is at a base map layer to our map project. We will use the quick map services plug-in to add a base map created by Stamen design. QGIS uses a plug-in model to extend the functionality of the basic software. Most plug-ins are contributed by members of the QGIS community and many extend functionality by adding interactivity with external services like geocoding , routing, and base map services.

1. On the **Main menu** of **QGIS**, find the **Plug-ins** menu and open the **Manage and install plugins** dialogue.  
2. In the search box at the top of the dialogue, search for the term "QuickMapServices"    
3. The search should return a plug-in called "QuickMapServices." 
4. Click on the QuickMapServices plug-in name and then click the install plug-in button
5. Once the plug-in has successfully installed, Close the plug-in management dialog.

![](./media/pluginMenu.png)  

### Add a basemap service layer

1. Installing the **QuickMapServices** plug-in should have added a new menu item to the QGIS main menu called "Web".
2. Click on the web menu and from the **QuickMapServices** item select "**Settings**."
3. Select the "**More Services**" tab and click on the "**Get contributed pack**" button. This will download a large list of web map services that can be used directly into GIS as base maps.  
![](./media/contribpack.png)  
4. Once the contributed pack has been downloaded click **Save** to close the dialog.
5. Now return to the quick map services menu, and select the **Stamen> Stamen Toner Lite** base map.

![](./media/stamenbasemap.png)

### Add an existing data layer
Now we're going to add an existing data layer. The data layer that we will add describes our area of interest in this study. This layer Will provide us with a convenient way to orient our data frame to the area that we are interested in as well as providing a way to limit the processing extent of certain geo-processing tools.

1. In the **QGIS Browser panel**, find the data folder for this workshop (Hint: look for the "**Project Home**" folder)a nd double-click on the **study_area.shp** file, to add it to your **map project**.
2. In the **Layers panel**, right-click on the **study_area layer** and select "**Zoom to layer**."
3. On the **Main menu**, enable the **Layer styling panel** from the **Layer>Panels menu**. 
4. In the **Layer styling panel** select **Simple fill** from the panel at the top, and change the **Fill style** to "**No brush**." If you would like you can also change the **Stroke color** & **Stroke width** of the stroke to make it more visible against the black-and-white basemap.
5. **Save** your **map document**.

![](./media/studyareaadd.png)

### Explore navigation tools

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

### Scale

When zooming in or out, the Scale Values at the bottom page change. Remember
that the bigger the number (1:60,000,000), the larger the area being displayed.
Although 60,000,000 is bigger than 60, a scale 1:60,000,000 is a small scale and
1:60 is a large scale because the division of 1/60,000,000 is smaller than 1/60.

![](./media/image20-drop-shadow.png)

![](./media/image22.png)  The **Zoom to Layer** to a specific layer extent.

![](./media/image23.png)  The **Zoom Last** and ![](./media/image24.png) **Zoom Next** works as a Redo or Undo tool **ONLY** for the Scale/Extent in your Map Canvas. This tool is particularly useful if you change your Map Extent inadvertently.

![](./media/image25.png)  The **Refresh Button** will reload your Map Extent

### Spatial Bookmarks

Often, we want to be able to move around in our data frame examining different parts of the map zooming in and out, and then returning to our primary area of interest. This can be easily accommodated through the use of spatial bookmarks. Here you'll create a spatial bookmark which allows us to quickly return to the area that we are interested in.

1. Previously we used the main menu to enable a panel. This time, try right-clicking in any empty area of the toolbar then scroll down and select the **Spatial Bookmarks panel** from the menu that is presented.
2. Right-click on your study_area layer and select **Zoom to layer**.
3. Click on the Add Bookmark button and rename the resulting Spatial Bookmark: "SOHO"  
![](./media/spatialbookmark.png)
4. Click on the **Zoom Full** button to zoom to the world, then use the **Zoom to bookmark **button to return to your Area of Interest.

### Working with CRS
Examine the Default CRS (web merc) change to UTM
#### Examine the CRS of a data layer
1. Right-click on the study area layer select the layer ∫ from the menu.
2. Click on the source tab on the left side of the properties panel, and note in the section called Geometry and Coordinate reference system that the CRS of this layer is:  

```EPSG:32630 WGS 84 / UTM zone 30N```  

![](./media/layercrs.png)
3. Click OK to close the Layer Properties Dialog  
4. On the main menu Open the Project Properties from the Project menu.  
5. Click on the CRS tab at the left and note that the project is in a projection called:  

```EPSG:3857 WGS 84 Pseudo-Mercator```   

*This is the projection of the basemap and is the default for the project because the basemap was the first layer that we added to the project.*  

![](./media/projectcrs.png)

#### Change the Project CRS  
1. Locate the CRS of the **Study_Area** layer in the "**Recently used coordinate reference systems**" section, or type the EPSG code "**32630**" into the Filter box at the top of the **Properties** dialog.  
![](./media/newprojectcrs.png)
2. Click on the ```EPSG:32630 WGS 84 / UTM zone 30N``` and then click OK to change the CRS of teh Project to teh same as the layer **Study_Area**.
3. Save your changes by clicking on the Save button ![](./media/savebutton.png) on the Project toolbar.  

### Create a data layer from an XY table?
Add the deathAddresses.csv 

1. Click on the **Add Delimited Text Layer** button ![](./media/delimitedlayer.png)to open the Data Source Manager dialog.
2. For **File Name**, browse to the **data** folder and select the **deathAddresses.csv**
3. Set the remainder of the settings as follows, and click **Add & Close** to import the layer:    

| setting | value |
|--------------------------:|--------------------------------------------------------------------|
| File Format:  | CSV |
| Record and Field Options: | "First records has field names" = true "Detect field types" = true |
| Geometry Definition: | Point coordinates: "X field" = 'xcoord, "Y field" = 'ycoord' |   


![](./media/datasourcemanager.png)  

![](./media/addedpoints-drop-shadow.png)

### Layer symbology
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

```addcontent: add drop shadow to points```

### Viewing the Attribute Table

1. Right-click on the **deathAddresses** layer in the **Layers** panel and select **Open Attribute Table**.
2. Note that you can sort fields, scroll, select by attributes, etc...

### Statistics on a field  

As mentioned, above, the **Num_Cases** field in the Death Addresses data indicates the number of deaths at each address in the dataset. You can get a simple statistical snapshot of the variable from the Attribute Table.

1. Close the Attribute Table
2. On the pull-down menu go to **Vector > Analysis Tools > Basic Statistics for Fields**
3. On the window select **Death Addresses** as the Input Vector layer and **Num_Cases** as the Target field.
4. **Click Run** and **Close** 
5. Look for the **Results Viewer** which should have been activated, and click on the **Hyperlink** to open the summary in a web browser.  
![](./media/resultsviewer-drop-shadow.png)   

## Creating spatial data from a scanned reference source map
### Finding a map
```addContent```  

* earthworks.stanford.edu
* DavidRumsey.com
* OldMapsOnline.com

### Finding an already georeferenced map
We'll start by looking at this map [[Gegend von London 1853](https://www.davidrumsey.com/luna/servlet/detail/RUMSEY~8~1~298861~90066747:Gegend-von-London-1853?sort=Pub_List_No_InitialSort%2CPub_Date%2CPub_List_No%2CSeries_No&qvq=w4s:/where%2FLondon%2B%252528England%252529%2Fwhen%2F1854;q:london%201854;sort:Pub_List_No_InitialSort%2CPub_Date%2CPub_List_No%2CSeries_No;lc:RUMSEY~8~1&mi=1&trs=2)] of London on [https://davidrumsey.com](https://davidrumsey.com). It already has a "**Georeferenced** version, which can be viewed by clicking on the **Georeferencer** button at the top of the page.



### Adding a DavidRumsey.com map to QGIS

Here is the **Web Map Tile Service WMTS URL** for the Gegend map:  

```http
https://maps.georeferencer.com/georeferences/435516159934/2019-02-19T17:27:12.514288Z/wmts?key=mpIMvCWIYHCcIzNaqUSo&SERVICE=WMTS&REQUEST=GetCapabilities
```
 
This URL provides access to the georeferenced map outside of the DavidRumsey.com website.

1. Select the WMTS URL, above, and copy it to your clipboard using right-click copy, or keyboard shortcuts, if you know them.  
2. On the Main Menu **Layer>Add Layer>Add WMS/WMTS Layer** to open the **Data Source Manager**
3. Click on teh **New** button to open the **Create a New WMS/WMTS Connection** dialog:  

| Setting | Value |
|--------:|----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Name: | Gegend Map |
| URL: | ```https://maps.georeferencer.com/georeferences/435516159934/2019-02-19T17:27:12.514288Z/wmts?key=mpIMvCWIYHCcIzNaqUSo&SERVICE=WMTS&REQUEST=GetCapabilities``` |   

![](./media/createwmtsconnect.png)   

4. Click OK to dismiss the dialog and save the connection  
5. Click **Connect**  
![](./media/connectwmts.png)    

6. In the **Tilesets** tab, highlight the Gegend map WMTS layer item at the top and click **Add & Close** to close the dialog and return to the **QGIS Map Canvas**  
7. **Right-click** on the **Gegend von London 1853** layer in the **Layer panel** and select **Zoom to layer**  
8. Use the **Navigation Tools** to explore the map service at sevaral different scales and extents.  

### Georeference a map

Georeference the John Snow 1854 SOHO map for digitizing the water pump locations.

1. On the **Main Menu**, go to **Raster>Georeferencer** to open the **GDAL Georeferencer**
2. Click on the **Open Raster** button  ![](./media/openraster.png) and browse to the **/data/** folder, select the **snow_map.png** and click **Open**
3. Use the Zoom tool to Zoom to the upper-right corner of the John Snow Map, around the SOHO Square
4. Click on the Add Point tool ![](./media/addgcp.png) and click on the upper right corner of the outside boundary of SOHO Square, as shown below:
![](./media/addpointdialog-drop-shadow.png)  
5. Click on the **From Map Canvas** button to switch back to the main QGIS Window
6. Zoom to the same are of your Map Canvas, *preferably using your mouse wheel or keyboard shortcuts so you don't deactivate the Add Point tool, but you can always go back to the Georeferencer window and reactivate it* 
7. Place **Ground Control Points** in each corner of the map, switching between the two windows using the **Add Point** tool, as needed. Add a final point somewhere near the center of the map.
![](./media/georeferencer.png)  
8. Click on the **Save GCP Points As...** button and save the points table as ```snow_map.png.points``` in your **/data/** folder.
9. Click on the **Transformation Settings** button ![](./media/transform.png) and examine the settings. The defaults should be fine, as follows:  

| Setting | Value |
|---------------------:|--------------------|
| Transformation Type: | Polynomial 1 |
| Resample Method: | Nearest Neighbor |
| Target SRS: | EPSG:4326 - WGS 84 |


10. Click on the **Start Georeferencing** button ![](./media/starttransform.png) to start the georeferencing of your image and add it to the Map Canvas.
11.  


### Digitize features from a georeferenced map
### Labels

## Exploration and basic analysis of spatial point patterns
### Spatial Allocation with Thiessen polygons (using/controlling geoprocessing tools)
### Spatial Joins
### Summary Statistics cased
### Spatial mean & standard distance
### Hotspot mapping using spatial interpolation

## Creating a map layout

### More Symbology
### Customizing page options
### Adding a Legend
### Adding a Table
### Adding a Scalebar
### Adding text (citations)
### Adding a Neatline
### Export options and formats

