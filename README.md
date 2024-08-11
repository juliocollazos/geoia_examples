<img src="./logo.png" alt="Logo" width="400"/>

# GeoIA Examples
#### ⚠️ Arreglar introducción
#### This repository aims to show several of the current functionalities for various geographic processes with the ability to automate through the use of LLMs and libraries that provide functionalities in everyday tasks such as land cover classification.
> **⚠️Warning**:
> The examples 1 and 2 will be worked out using [Vizly](https://vizly.fyi/app)

## Example one - Universal Mill List interactive dashboard
> The material for this exercise can be found in the folder named [Example_One](./Example_one)
##### The [gadm_countries.geojson](./data/gadm_countries.geojson) was generated using the [GADM oficial data](https://gadm.org/download_world.html) and executing the following ogr2ogr command:
```bash
ogr2ogr -f GeoJSON c:\...\gadm_country.geojson c:\...\gadm_410.gpkg -dialect sqlite -sql "SELECT NAME_0 AS country_name, ST_SimplifyPreserveTopology(ST_Union(geom),0.05) AS geometry FROM gadm_410 GROUP BY country_name"
```
>**🚨Promp 1:**
>

## Example 2 - Forest cover dashboard
> The material for this exercise can be found in the folder names [Example_two](./Example_two)
> 

## Example 3 - Segment Anything Model (SAM)

