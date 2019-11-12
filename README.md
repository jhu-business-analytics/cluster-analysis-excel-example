# Cluster Analysis with Excel

## Overview
In our linear regression examples we use different independent variables in our data to help predict outcomes in dependent variables, which we used in past examples to try and predict Baltimore City employee annual and earned salaries in specific departments and in specific positions in Baltimore City government. However, what this doesn’t tell us is how these predictions, and how data and trends in general, compare with employees’ salaries and earnings in other city governments. We can use a __cluster analysis__ to mathematically determine how Baltimore City and it’s employment and population demographics are “related” to other cities around the US and group together in a predictable way, which, in turn, can help us identify whether high overtime earnings in the Baltimore Police Department are due to factors specific to Baltimore or if these are outcomes related to specific demographics or trends in similar cities. 

 ## Cluster Analysis
There are several types of cluster analyses, and here we will use *Microsoft Excel’s Solver Function* to perform a __k-means clustering__ analysis to group US cities by population size, density, and growth. For a cluster analysis we will have specific data points that we are interested in clustering (e.g. US cities) and their related data points that will help us determine the clusters (e.g. population size, population density, population growth, police officer population, crime rates, etc.). 

In a k-means clustering analysis, we essentially group our data based on the distances between the data point and a cluster __anchor__. To illustrate this, we’ll look at a cluster with only two variables (2018 population and 2017-2018 population change) to cluster our cities by:

![alt text](https://github.com/jhu-business-analytics/cluster-analysis-excel-example/blob/master/screenshots/cluster_scatter.png)

Here, we create a scatter chart of the 60 most populous cities as of 2018, plotting their 2018 population (x-axis) against their 2017-2018 population change (y-axis). From the distribution, we can make some guesses about how individual or clusters of data points are grouped together, but we can’t be sure which of these are closely related based on this graph alone.

![alt text](https://github.com/jhu-business-analytics/cluster-analysis-excel-example/blob/master/screenshots/cluster_guess.png)

We might guess that this specific data set clusters into 4 groups with the groups (represented by the red circles) and centers around the four anchor points (burgundy “x”s), which represent the average of each cluster. However, we see that some of the clustering overlap becomes less apparent when we try to separate the data in close-together clusters. At a high level, to mathematically calculate how these data points group together with the k-means clustering method, we:

1. Define a number of __anchor points__ around which to center our clusters. The number of anchor points determines the number of clusters for our analysis and can be any number that we select, however, if we select too few (e.g. 1) or too many (e.g. equal to the number of data points) clusters, this may not give us any insight into our data.

![alt text]()

2. Calculate the distance between each data point and each of the anchor points. 

![alt text](https://github.com/jhu-business-analytics/cluster-analysis-excel-example/blob/master/screenshots/cluster_distances.png)

3. Assign all of the data points to a cluster anchor point based on which anchor-data point distance is the smallest. This clusters all of our data into the number of anchor points we’ve determined up front and allows us to better understand how our data is related and how we might want to further our analysis. 

![alt text](https://github.com/jhu-business-analytics/cluster-analysis-excel-example/blob/master/screenshots/cluster_with_anchors.png)
 
After we conduct a cluster analysis we may want to re-run the analysis to include more or less clusters than we originally defined based on how the data groups.

In this example we’ll review how to prepare data for and how to conduct a cluster analysis in Excel in addition to how to interpret the results of our cluster analysis for related strategies and additional analysis.

### Data Sources and Use
For our cluster analysis example we combine datasets from:

 - The __[American Community Survey](https://factfinder.census.gov/faces/nav/jsf/pages/guided_search.xhtml)__: from this we extract the population of the 60 most populous cities in the United States in 2017 and 2018 and the growth in these cities between 2017b and 2018
 - __[World Population Review](http://worldpopulationreview.com/us-cities/)__: this gives us the land size of all US cities, which we merge with the population size data

to build a data set of the 60 most populous cities (Baltimore is ranked #30), their populations in 2017 and 2018, the population change from 2017-2018, and their land mass. This will give us insight into how cities are grouped based on the number of people (e.g. Police Officers, etc.) needed to govern any given population and how this might be changing for different cities. Once we know what cities are grouped with Baltimore, MD, we can look further into the makeup of these cities’ public service positions and compare them with Baltimore, MD. Furthermore, we can perform additional cluster analysis with US cities to group them by volume of 911 calls, volume of different types of crime, racial and income demographics, police department size, and city government overtime earnings to gain further insight into how Baltimore compares with its “peer” cities and what initiatives may be successful for different population types. 

## Preparing the Data
Our original data for this analysis gives us:
 - names of the city and state for the 60 most populous incorporated cities in the US
 - the population estimate for 2017
 - the population estimate for 2018
 - the population change from 2017-2018 as a number 
 - the population change from 2017-2018 as a percent
 - the land area in square miles of the city

A sample of this data is below: 
![alt text](https://github.com/jhu-business-analytics/cluster-analysis-excel-example/blob/master/screenshots/original_data.png) 

Before we can conduct a cluster analysis, we’ll first need to prepare our data such that our cluster analysis produces a fair assessment of our data. Because the data points that we use to determine the clusters may have drastically different scales (e.g. on the order of millions vs on the order of tens), we usually want to __normalize__ our data to accurately and fairly compare the influence of all of our selected values.

To do this in Excel, we’ll calculate the __z-score__ for each of the data points that we want to include in our cluster analysis, which essentially calculates how far away this data point is from the data’s mean. 




