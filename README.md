<img src="./Data/logo.png" alt="Logo" width="400"/>

# GeoIA Examples
This repository is designed to showcase the capabilities of current technologies in automating various geospatial 
processes. It focuses on generating statistical analyses and spatial visualizations, including outputs such as 
interactive maps, graphical representations, and base cartography. By leveraging large language models (LLMs) and 
specialized libraries, the repository provides efficient solutions for everyday geospatial tasks.
> **⚠️Warning**:
> The examples 1 and 2 will be worked out using [Vizly](https://vizly.fyi/app) 
> and the example three will be worked out using a Jupyter Notebooks

## 1. Universal Mill List interactive dashboard
The material for this exercise can be found in the folder named [Example_One](./Example_one) <br>
The [gadm_countries.gpkg](./Example_one/gadm_countries.gpkg) was generated using the [GADM oficial data](https://gadm.org/download_world.html) and was processed executing the following [ogr2ogr](https://gdal.org/programs/ogr2ogr.html) command:
```bash
ogr2ogr -f GPKG c:\..\gadm_country.gpkg c:\..\gadm_410.gpkg -nln "gadm_country" -nlt MULTIPOLYGON -dialect sqlite -sql "SELECT NAME_0 AS country_name, ST_SimplifyPreserveTopology(ST_Union(geom),0.05) AS geom FROM gadm_410 GROUP BY country_name" -explodecollections
```
### **🚨Promp 1:**
> I am working on a geospatial data visualization project and need a Python script to load and process information 
> about palm oil mills in Malaysia and Indonesia. The script should first load a CSV file from the following 
> URL: https://raw.githubusercontent.com/juliocollazos/geoia_examples/main/Example_one/UML_data.csv. 
> This file contains information about the mills, with relevant columns including 'Mill Name', 'RSPO Status', 
> 'Latitude', 'Longitude', and 'Country'. The script should convert the 'Latitude' and 'Longitude' 
> columns to numeric values. If there are columns that do not contain valid information, such as those with 
> NaN values in 'Latitude' or 'Longitude', these columns should be removed from the DataFrame.
### **🚨Promp 2:**
>After cleaning the data, the script should filter the DataFrame to include only rows where the 'Country' column 
> is either 'Malaysia' or 'Indonesia'. These filtered data should then be converted into a GeoDataFrame using 
> GeoPandas, transforming the 'Longitude' and 'Latitude' columns into point geometries (geometry) with the 
> EPSG:4326 coordinate system.
### **🚨Promp 3:**
>Next, the script should load the country boundaries from a GeoPackage file located 
> at https://github.com/juliocollazos/geoia_examples/raw/main/Example_one/gadm_country.gpkg. 
> This file contains a column called 'country_name', which should be used to filter the boundaries to 'Malaysia' 
> and 'Indonesia'. 
### **🚨Promp 4:**
> Once the data processing is complete, the script should create an interactive map using Folium. 
> The map should be centered on the average coordinates of the 'Latitude' and 'Longitude' columns from the 
> filtered points, with an initial zoom level of 5 and using OpenStreetMap tiles. On the map, the country boundaries 
> should be added as a layer named 'Country Boundaries', with a black border ('color': 'black') and a yellow fill 
> with 30% opacity ('fillColor': 'yellow', 'fillOpacity': 0.3). The country name ('country_name') should appear as a 
> popup when clicking on the respective area on the map.
>
> In addition, the script should create a MarkerCluster named 'Palm Oil Mills' to group the points corresponding 
> to the mills. For each mill, a marker should be added to the MarkerCluster that displays a popup containing 
> the mill's name ('Mill Name'), its RSPO certification status ('RSPO Status'), and the country ('Country').
>
> Finally, the script should include a layer control (LayerControl) that allows toggling the visibility of the 
> 'Country Boundaries' layer and the 'Palm Oil Mills' layer. Once the script is generated, it should be executed, 
> and the resulting map should be displayed on the screen.

### The result will be something like:
<img src="./Data/Ejemplo1.png" alt="Logo" width="400"/>

## 2. Réunion tree cover loss analysis
> The material for this exercise can be found in the folder named [Example_two](./Example_two)


## Example 3 - Using geoai in python
ogr2ogr -f GPKG 
