# Optimizing-2020-Polling-Locations


__Link to the project demo__ : https://arcg.is/18z5yT (includes interactive visualizations that takes a couple minutes to load)

Final project from the class DSC 170: Spatial Data Science. The Jupyter Notebook of the source code can be viewed on the 'project_notebook_final.ipynb' file.

__Contributors: Renaldy Herlim, Siddhi Patel__

## Introduction

In this project, we wanted to explicitly answer these hypothesis questions:
Using GIS and Data Science methods, can we optimize the placement of polling locations to emphasize the weight of permanent in-person voters? 
Do our planned locations differ from that of the official 2020 polling locations?

Our plan of attack to answer these questions is to format the problem as a location-allocation problem, where we weight our locations based on the rate of in-person voters in a certain election precinct. This will help us answer the first question since we’ll be emphasizing the weight of permanent in-person voters this way. We hope to find that the polling locations we develop will differ from that of the official 2020 polling locations because we used a more quantitative approach in determining their locations. This finding would be important so that in the future, elections departments can efficiently place polling locations in areas that are more equitable for all in-person voters. 

This project is catered towards local government departments that are in charge of finding polling places for elections. According to San Francisco’s Department of Elections, a number of election precincts are set up based on voter registration during election years. It is then up to the Elections Department to find volunteers for polling locations within those precincts. However, that essentially means that polling locations are chosen at random within election precincts rather than intentionally chosen to maximize in-person voter attendance. In this project, we aim to plot polling locations within precincts that can maximize voter attendance based on voter registration data. This would be beneficial in order to increase the weight of in-person voters and to provide them with more equitable polling locations. 


## Datasets

All of the datasets are in ArcGIS FeatureLayer format, they are hosted by, or stored on, ArcGIS Online. These layers offer flexibility, scalability, and compatibility across ArcGIS, which is what the project is mostly handled with.

__San Diego County 2020 Polling Locations__: This point layer is published by SanGIS to depict coordinates for the polling locations in SD county. 
Link: https://ucsdonline.maps.arcgis.com/home/item.html?id=c06c671a9bab46c7a4d049b104836f11
Number of Spatial Objects: 573

__San Diego County 2020 Elections Precincts__: This layer would help us see the boundaries of the precincts for 2020. We can compare these precincts to demographic data from the Census and see if certain incomes or races are clumped into different precincts. 
Link: https://ucsdonline.maps.arcgis.com/home/item.html?id=c06c671a9bab46c7a4d049b104836f11
Number of Spatial Objects: 1,153

__SANDAG San Diego County Existing Locations/Land Use Data__ : This dataset contains all the existing locations in San Diego county, categorized into the type of institutions (Education, Recreational, etc.). Last updated December 2019. 
Link: https://sdgis-sandag.opendata.arcgis.com/datasets/existing-landuse-1
Number of spatial objects: 119,298


## Libraries and Modules

Pandas - to perform in-depth analysis as well as get a better understanding of the spatial dataframes and shapefiles that we are going to be importing into our project notebook. Pandas will help us pre-process the data better. 

Seaborn - to visualize our data nicely

ArcGIS Features Manage_data module - to use dissolve_boundaries in order to get the correct amount of polling locations.

ArcGIS Geoenrichment - to get more information regarding areas in San Diego county, like getting demographic, income, race, and other data on polling locations. This helps us get a better idea of how our polling locations differ from that of the official polling locations. 

ArcGIS Features Analysis module - to use find_existing_locations, merge_layers, and overlay_layers as well as aggregate_points and create_buffers to summarize and get statistics on certain areas of interests and to find relevant voting locations that we are going to use in our analysis (NOTE: We did much of these functions in ArcGIS Online since it was easier to visualize. More information included below).

ArcGIS Network - In order to use the feature solve_location_allocation. (NOTE: We did much of the location allocation in ArcGIS Online since it was easier to visualize. More information included below)

ArcGIS Storymaps - to create our presentation for the project findings, we can easily store all our map layers in one location as well as present our analysis in a more organized and presentable way.
