# Project 1: Modeling the population and geography of Senegal and its districts

I chose to examine Senegal because, with a population of 16 million, it is a relatively populous
developing country in West Africa. Furthermore, I became very interested in Senegal's development
when I learned through my initial research that various businesses and humanitarian groups have
taken an interest in it due to its rapidly rising population and status as a cultural center in
West Africa. Finally, Senegal contains a sizable amount of both rural and urban areas which I
thought could make for some insightful analysis.

## Creating a Geometric Bar Plot

This graphic consists of a geospatial map of Senegal and its regions with a geospatial map containing
a heatmap that indicates each region's population density; and a geometric bar plot of the percent of
the population of Senegal that is located in each region sorted from highest to lowest.

This graphic shows that the majority of Senegal's population is concentrated in the Dakar and Thies
regions in the west coast where its capital, also named Dakar, and other largest cities are located
while the east side of the country is considerably less populated with kedougou being the least
populated region.

![alt text](https://raw.githubusercontent.com/Seabass1000/ABM/master/1-Geometric%20Bar%20Plot.png)

### Stretch goal 1: A Geometric Bar Plot of the Population Distribution of Senegal's Regions and Districts

This bar plot provides further information about the distribution of Sengal's population by also
including subgroups of the district's in each region. This plot further highlights the contrast
between the population of Gabon's western and eastern regions.

![alt text](https://raw.githubusercontent.com/Seabass1000/ABM/master/3-P1_stretch_1.png)

### Stretch goal 2: A 3-dimensional Model of the Population Density of Senegal and its Regions

The 3D plot below also visualizes Senegal's population density. In addition to having a higher
instensity on the heat map, regions are taller if they have a higher population.

![alt text](https://github.com/Seabass1000/ABM/blob/master/p1.gif)

## Defacto Descriptions of Human Settlements

In this part of the project I modeled the "defacto" descriptions of human settlements in Sengal's kedougou
region by showing the areas in which people congregate. I chose to focus my analysis to the kedougou
region because it is Senegal's least populated and most rural region (my research indicated that
it is teaming with wildlife). This provided two benefits: it is computationally easier to examine
a region with a small population and, more importanly, I wanted to examine a lesser populated rural
area because of my belief that those areas usually get overlooked by nationally representitive surveys.

I began by first modeling the kedougou district within the kedougou region. These plots show the
population density of kedougou. The first plot is a population raster on top of a map shapefile and
the second uses a shapegilr it to calculate the population density with rpoint and plots this on
top of the first plot. This paints a good picture into where people are concentrated.

![alt text](https://raw.githubusercontent.com/Seabass1000/ABM/master/thas.png)
![alt text](https://raw.githubusercontent.com/Seabass1000/ABM/master/This.png)

I then ploted the countour lines, lines representing the De Facto human settlements over the density image.
I filtered the map to remove polygons that are outliers and noise, such as those with absurdy high or low
densities and populations. I used this information to map the Urbanized areas in kedougou eith its population
densities.

![alt text](https://github.com/Seabass1000/ABM/blob/master/6-urban_area_polygons_and_density.png)
![alt text](https://raw.githubusercontent.com/Seabass1000/ABM/master/5-Dfcto_urbn_sttlments_250.png)

###  Saraya, Senegal
![alt text](https://raw.githubusercontent.com/Seabass1000/ABM/master/7-saraya250_theonlyone.png)

## Urbanized areas through Saraya and kedougou, Senegal
![alt text](https://raw.githubusercontent.com/Seabass1000/ABM/master/8-combined.png)

## Zipf's Law
![alt text](https://raw.githubusercontent.com/Seabass1000/ABM/master/Zipf.png)

## Public Roads and Health Care Facilities
![alt text](https://raw.githubusercontent.com/Seabass1000/ABM/master/9-Road_and_Health.png)
