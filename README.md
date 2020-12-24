# Optimizing-2020-Polling-Locations
Final project from the class DSC 170: Spatial Data Science. Contributors: Renaldy Herlim, Siddhi Patel

__Introduction__
In this project, we wanted to explicitly answer these hypothesis questions:
Using GIS, can we optimize the placement of polling locations to emphasize the weight of permanent in-person voters? 
Do our planned locations differ from that of the official 2020 polling locations?

Our plan of attack to answer these questions is to format the problem as a location-allocation problem, where we weight our locations based on the rate of in-person voters in a certain election precinct. This will help us answer the first question since we’ll be emphasizing the weight of permanent in-person voters this way. We hope to find that the polling locations we develop will differ from that of the official 2020 polling locations because we used a more quantitative approach in determining their locations. This finding would be important so that in the future, elections departments can efficiently place polling locations in areas that are more equitable for all in-person voters. 

This project is catered towards local government departments that are in charge of finding polling places for elections. According to San Francisco’s Department of Elections, a number of election precincts are set up based on voter registration during election years. It is then up to the Elections Department to find volunteers for polling locations within those precincts. However, that essentially means that polling locations are chosen at random within election precincts rather than intentionally chosen to maximize in-person voter attendance. In this project, we aim to plot polling locations within precincts that can maximize voter attendance based on voter registration data. This would be beneficial in order to increase the weight of in-person voters and to provide them with more equitable polling locations. 
