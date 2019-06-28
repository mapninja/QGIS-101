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

### Georeference a map (Georeferencer seems to not be working properly)

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



### Digitize features from a georeferenced map

If the last section didn't go well, add the ```John_Snow_Map.tif``` from the **/backup_data/**  

1. On the **Main Menu**, go to **Layer>Create Layer** and select the **New Shapefile** option
2. Use the following settings:

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

### Add points to your shapefile

1. Right-click on the water_pumps layer and selelct **Toggle Editing**
2. Click on the Add Point Feature button ![](./media/editpoint.png)and add a point for one of the Water Pumps in the John Snow map. 
3. Label the point with the street it is on in the **Feature Attributes pop-up** and click ok to create the feature.
![](./media/featureattributes.png)
4. Continue digitizing Until you have captured all 12 water pumps in the map.
5. Right-click on the water_pumps layer and selelct **Toggle Editing** and save your edits when you are prompted.

### Labels

1. Click on the **water_pumps** layer to activate it in the **Layer Styling** panel
2. Click on the **Label** tab of the **Layer Styling** panel
3. Change the Label option to **Single labels**
4. Set **Label with:** to the 'label' field.
5. Increase the **Text Size** to **14**
6. Click on Buffer tab and enable the **Draw text buffer** option. 

![](./media/labels.png)

## Basic spatial data analysis

### Voronoi (Thiessen) polygon (Spatial Allocation)

Thiessen polygons allocate space in an area of interest to a single feature per
polygon. That is, within a Thiessen polygon, all other features are closer to
the point that was used to generate that polygon than to any other point in the
feature set. In this case, we will create a set of Thiessen polygons based upon
the locations of the Water Pumps in our project.

1. On the Main Menu go to menu go to **Processing \> Toolbox**
2. Go to the **Processing Toolbox Window** and change the view from **Simplified Interface** to **Advanced Interface.**
3. Search for **Voronoi.**
4. **Double–click** the **Voronoi polygons** tool under **Grass commands.**
5. On the v.voronoi tool window input the select **Water Pumps** as the **Input points layer.**

![](media/image004-drop-shadow.png)

On **Grass region, click the 3 dots** and select **Use layer/canvas extent.**

1.  On the **Select extent window,** scroll down to find **Study Area.**

2.  **Click OK**

3.  **Click the 3 dots** besides the Voronoi diagram option, and **select Save
    to file.**

4.  Browse for the **EX_02_Snow_Map folder** and **save** the shapefile as
    **Water \_Pump_Voronoi.**

5.  **Click Run**

![](media/image005-drop-shadow.png)

**Open** the Attribute Table of the **Water_Pump_Voronoi** to explore how each
Voronoi Polygon has the name of the pump enclosed.

###  Spatial Join (Point Aggregation)

Now that you have created the Thiessen polygon layer, you will “allocate” each
of the deaths to one of the Thiessen polygons. To do this, we will use the
**Spatial Join** tool.

![](media/image006-drop-shadow.png)

On the pull-down menu go to menu go to **Vector \> Data Management Tools \> Join
attributes by location**

1.  Select **Death Addresses** as the Target vector layer and
    **Water_Pump_Voronoi** as the Join vector layer.

2.  **Click Browse** to save the **Output Shapefile** as **Deaths_Allocated** in
    your **Data** Folder.

3.  **Click OK**

4.  Click **Yes** to add the new layer to the TOC (Table of Contents) and Close
    the Join the attributes by location window.

5.  The resulting layer is added to the Map Canvas. **Open** its **attribute
    table** to confirm that the attributes of the Water Pumps have been
    transferred (Hint: OBJECT ID_2, Name).

### Summary Statistics

![](media/image007-drop-shadow.png)

Finally, we would like to summarize the deaths in the outbreak, grouping our
summary by the name of the Water Pump that each Death Address is nearest.

1.  On the pull-down menu go to **Plugins\> Manage and install plugins.**

2.  On the Plugins window search, type **Group Stats** and select it.

3.  Click on **Install plugin.**

4.  Close the **Plugin Window.**

![](media/image008.png)

>   After the installation a **GroupStats Tool** appears on the Vector Toolbar.

1.  **Click** the **Group Stats tool**

2.  **Select Deaths_Allocated** as Layer.

![](media/image009-drop-shadow.png)

Dag from **Fields** to **Column**: average, count and sum. On **Rows,** drag
Name (originally from the Water_Pump data layer), and on **Value** drag
**Num_Cases.**

1.  **Click** on **Calculate** to visualize the summary table.

2.  **Click** the Sum field header on the resulting table to **Sort descending**
    on the **SUM_Num_Cases** field.

Note that the **Broadwick Pump** has the highest value for two of three
significant attributes: **Count** (No. of households), **Sum** (Total Deaths),
and **Average** (Mean Deaths per Household).

1.  On the **Group Stats Window,** go the **Data\> Save all to CSV file. Save**
    the **Ouput Table** to your **Data** Folder and name it
    **Deaths_Summary_by_Pumps**.

2.  **Close** the Group Stats Window

## Spatial Central Tendency

### Spatial Mean (Mean Center)

“The [mean center](https://desktop.arcgis.com/en/arcmap/latest/tools/spatial-statistics-toolbox/h-how-mean-center-spatial-statistics-works.htm) is the average x- and y-coordinate of all the features in the study area. It's useful for tracking changes in the distribution or for comparing the distributions of different types of feature”

![](media/image010-drop-shadow.png) 

On the pull-down menu go to menu go to **Vector \> Analysis \> Mean
coordinate(s)**

1.  Select **Death Addresses** as the Input vector layer.

2.  Leave the **Weight field** and **Unique ID field** as **Optional.**

3.  **Click Browse** to **save** the Output Shapefile as:
    **Deaths_Spatial_Mean** to the **Data** Folder**.**

4.  **Click OK** to calculate the **Mean Center** and **Close**.

5.  Change the **Symbology** for the **Deaths_Spatial_Mean layer** to something
    that contrasts with the other symbologies.

### Weighted Spatial Mean

1.  **Run** the **Mean Center tool** again, this time assigning the
    **Num_Cases** field as the **Weight Field**.

2.  **Save** the **Output Shapefile** to the **Data** folder and name it
    **Deaths_Weighted_Spatial_Mean**.

3.  **Apply a symbology** to the **Deaths_Weighted_Spatial_Mean layer**.

### Standard Distance

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

### Creating a surface from Point Data to Highlight “Hotspots”

![media/image14.png](media/image014-drop-shadow.png)

Kernel Density

The Kernel Density Tool calculates a magnitude per unit area from the point
features using a kernel function to fit a smoothly tapered surface to each
point. The result is a raster dataset which can reveal “hotspots” in the array
of point data.

1.  Go to the **Processing Toolbox Window** and **type** to search **Kernel
    Density Estimation (SAGA)** and **double click** to open the tool window.

2.  **Select** the **Deaths_Allocated** layer as the **Points** features.

3.  Select **Num_Cases** as the **Weight Field.**

4.  Set the **Radius** option to **50** (this is in meters).

5.  On the **Output Extent** option, click the 3 dots and select **Use
    layer/canvas extent.**

6.  On the resulting window search for **Study Area** and **Click OK.**

![](media/image015-drop-shadow.png)

Set the **Cellsize** to 10 (this is also in meters)

1.  On the **Kernel Option click** the 3 dots and select **Save to File.**

2.  **Save** the **Output Raster** to the **Data Folder** as **Kernel_Density.**

3.  **Click Run** to run the Kernel Density tool.

4.  **Right Click** the **Kernel_Density layer** and **open** its
    **properties**.

![](media/image016-drop-shadow.png)

**Go** to the **Style Tab** and select

1.  **Render Type:** Singleband gray

    1.  **Color Gradient:** White to black

    2.  **Contrast enhancement:** Stretch to MinMax.

    3.  **Load min/max values:** Select min/max and click load.

    4.  **Hue:** Check Colorize and select a color of your choice

    5.  **Resampling:** Zoomed in **Bilinear.**

    6.  **Click OK**

![](media/image017-drop-shadow.png)



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

