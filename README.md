# Spatial Database Final Project

# Introduction
The Coastal Marine Zones dataset used in this notebook can be found here.

## What is a "Marine Zone Forecast"?

National Weather Service marine zones are specific, defined over-water areas contained in the various NWS marine forecast products. Each zone is identified by a text description and a Universal Generic Code (UGC), e.g. LONG ISLAND SOUND EAST OF NEW HAVEN CT/PORT JEFFERSON NY, ANZ330. Zones are divided to identify meteorlogically dissimilar areas. Marine Zone Forecasts outline the range of conditions which may be found within the entire zone. The size of a zone and the number of zones within a forecast product is a compromise between forecast accuracy and dissemination limitations.

The marine environment is defined as those waters that are saline and tide-affected. The coastal zone is defined as those areas of land which border the marine environment. The coastal zone extends inland to the first major change in topography beyond which coastal processes have little influence).

- Examples of coastal ecosystems: Estuaries, coastal dunes, rocky coasts, sandy beaches, coastal cliffs, intertidal (littoral) areas.
- Examples of marine ecosystems: Coral reefs, benthic, kelp forests, rocky reefs, continental shelves, sea-mounts, hydro-thermal vents, open oceans, polar oceans.
- Oceanic zones: Epipelagic, mesopelagic, bathypelagic, abyssalpelagic, hadalpelagic.
- Coastal zones: Inshore, littoral, foreshore, backshore.

From description about Coastal zones. A coastal zone is the interface between the land and water. These zones are important because a majority of the world's population inhabit such zones. Coastal zones are continually changing because of the dynamic interaction between the oceans and the land. Waves and winds along the coast are both eroding rock and depositing sediment on a continuous basis, and rates of erosion and deposition vary considerably from day to day along such zones. The energy reaching the coast can become high during storms, and such high energies make coastal zones areas of high vulnerability to natural hazards. Thus, an understanding of the interactions of the oceans and the land is essential in understanding the hazards associated with coastal zones. Tides, currents, and waves bring energy to the coast, and thus we start with these three factors.

## Abstract:

Coastal marine forecasts and Special Marine Warnings are issued by zone, each zone identified by a text description and a Universal Generic Code (UGC). These forecasts are prepared by the individual Weather Forecast Office responsible for the zone.

## Purpose:

To deliniate the coastal marine zones for the use in creating coastal marine forecasts and warnings.

## Programming
## GeoPandas

GeoPandas is an open source project to make working with geospatial data in python easier. GeoPandas extends the datatypes used by pandas to allow spatial operations on geometric types. Geometric operations are performed by shapely. Geopandas further depends on fiona for file access and descartes and matplotlib for plotting.

The goal of GeoPandas is to make working with geospatial data in python easier. It combines the capabilities of pandas and shapely, providing geospatial operations in pandas and a high-level interface to multiple geometries to shapely. GeoPandas enables you to easily do operations in python that would otherwise require a spatial database such as PostGIS.

## OGC SimpleFeatures

A standard that specifies a common storage and access model of mostly two-dimensional geographical data (point, line, polygon, multi-point, multi-line, etc.) The formats were originally defined by the Open Geospatial Consortium (OGC) and described in their Simple Feature Access and Coordinate Transformation Service specifications.

The standard defines a model for two-dimensional simple features, with linear interpolation between vertices. The data model defined is a hierarchy of classes. This part also defines representation using Well-Known Text (and Binary). WKT/WKB: Well Known Text and Well Known Binary

Well-known text (WKT) is a text markup language for representing vector geometry objects on a map, spatial reference systems of spatial objects and transformations between spatial reference systems. A binary equivalent, known as well-known binary (WKB), is used to transfer and store the same information on databases, such as PostGIS, Microsoft SQL Server and DB2. The formats were originally defined by the Open Geospatial Consortium (OGC) and described in their Simple Feature Access and Coordinate Transformation Service specifications. Implications for PySpark data de/serialization & un/marshalling

When using pyspark we want have to send data back and forth between master node and the workers which run jobs on the JVM. In order to simplify this rather than sending Python or more precisely Shapely objects we will use WKT. It works with one the libraries I am using today to perform Spatial Joins.

## References :

What is a "Marine Zone Forecast"? - http://www.nws.noaa.gov/om/marine/faq.htm#28
Coastal zones By Prof. Stephen A. Nelson - http://www.tulane.edu/~sanelson/Natural_Disasters/coastalzones.htm

## Overview of Coastal, Offshore and High Seas Marine Zones

- Date dataset : june, 16th 2018
- Shapefile Type: Polygon
- Data source: Coastline derived from US Counties
- Naming convention: mzddmmyy (coastal marine zones), ozddmmyy (offshore zones), hzddmmyy (high seas zones) where ddmmyy = day-month-year

- NWS Specifications: NWSI 10-302
- Description: The NWS issues marine forecasts, watches, warnings and advisories for a set of defined zone for offshore and coastal waters of the U.S.
