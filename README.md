# urban_tree_shade_analysis

Code and materials related to shade model analysis by Dr. John Wilson's team at USC

Storymap URL:https://storymaps.arcgis.com/stories/7f5c570fa0ff4d2eb918f933d869a2d6

Project goals and expected outputs：
Design and implement methods to estimate the shadow surface provided by (a) terrain surfaces (including elevated highways), (b) buildings, and (c) existing tree canopy. The purpose is to conduct the analysis every 10 minutes from sunrise to sunset over a calendar year so that we can use a raster grid to summarize the cumulative hours of shade currently provided by all 6 communities. Dr. John Wilson will specify the methods used and the general characteristics of the data, Yifan Yang will lead the effort to build these methods so we can write papers and improve our description of communities and their greening opportunities.

Manuscript submitted to the journal, describing the methods and values of the output, and the spatiotemporal raster stack we will deploy to further our work, for example, highlighting areas that could be better colored and their ownership status, as well as these candidate sites Whether you currently have a permeable or impermeable surface. These metrics will also be incorporated into the Canopy Scorecard of the Bezos Earth Fund’s work over the next year.

Boyle Heights is a working-class, predominantly Mexican American, youthful neighborhood of almost 100,000 residents east of Downtown Los Angeles in the City of Los Angeles, California.

Population: 92,785

Latitude: 34° 02' 2.04" N
Longitude: -118° 12' 19.26" W
https://latitude.to/map/us/united-states/cities/boyle-heights


la_sunset_and_sunrise_time.ipynb：
is a notebook-based python file whose function is to call the API to query and output the sunrise and sunset times at a certain point. This file is to query the time from sunrise to sunset every day in Los Angeles in 2023, and divides it every ten minutes; at the same time, we only take integer times here, for example, 6:54 in the morning will become 7:00, in the morning 6:48 will become 6:50. The same time at night is similar, 6:04 pm will become 6:00 pm.



auto_sun_shadowfrequency.ipynb：
completes the entire automation process. You only need to modify the name of the input file to automatically read the sunrise and sunset files. successfully running on the USC SSI PC 007
the code successfully running on the different computer, you can try to run the code named z46 or auto_sun_shadowfrequency, sometimes some pc need to take care SyntaxError: (unicode error) 'unicodeescape' codec can't decode bytes in position 2-3: truncated \UXXXXXXXX escape (<string>, line 33)
This code could successfully running for 1 day result in small test zoon(begin: 2:51pm 03212024 endtime: 7:22pm 03212024) when you want to calulate 1 year, the code still need to revise for one year



Session 1, sunrise and sunset times
This section discusses all things related to sunrise and sunset times.

Sunrise_Sunset_2023_LA：
A file containing the sunrise and sunset time points for Los Angeles throughout the year 2023. The same times are processed into integers.

Sunrise_Sunset_Intervals_2023_LA：
A file containing the sunrise and sunset time points of Los Angeles throughout 2023, and each day is a sheet. There are 365 sheets in total, and they are also divided every 10 minutes. Times are treated as integers.



Session 2, 3D modeling data sources and specific information, methodology
This section discusses how to go from shapefiles to built 3D models, discussing data details and methodology.




Session 3, Shadow area calculation, usage analysis of Sun Shadow frequency tool, and process automation.
This part mainly discusses the methodology, parameter settings, and potential problems of sun shadow frequency.

Extract the freeway height from a lidar dataset in ArcGIS Pro(DSM-DTM)
https://support.esri.com/en-us/knowledge-base/how-to-extract-the-tree-canopy-height-from-a-lidar-data-000030802

problem here: Lidar data convert to DEM and DSM, unit problem(need to check out)

Lidar data download from USGS
https://www.sciencebase.gov/catalog/item/5b5461bae4b05cbf87c1cbce

sampling value:
The value used in conjunction with the Sampling Type parameter to define the resolution of the output raster.
Z factor:
The factor by which z-values will be multiplied. This is typically used to convert z linear units to match x,y linear units. The default is 1, which leaves elevation values unchanged. This parameter is not available if the spatial reference of the input surface has a z datum with a specified linear unit.
I set up value 1, 1

LAS Dataset To Raster
https://pro.arcgis.com/en/pro-app/latest/tool-reference/conversion/las-dataset-to-raster.htm

2006DSM file name: means F drive has some many DSM, DTM, DEM data, including point, CAD, raster; tells how to get the height information from these value
You can find these data in area 4 and area6


checkpoint:

freeway use2006 DSM-DTM. What we want is that different segments have different heights. Width: measurement distance

buffer(direction data source(weight))    DEM DSM DTM Lidar unit zonal   Planetary computer Microsoft dem dsm(no study area)
https://planetarycomputer.microsoft.com/dataset/3dep-lidar-dsm
https://planetarycomputer.microsoft.com/account/request
Planetary computer Microsoft.docx could give you all detial, but useless for this project

USGS 3DEP Lidar Digital Surface Model
Sorry, no items matched your filter. Try adjusting the query parameters or expand the map area.

tree Yes! merge all the tree together! height 25 us feet， buffer distance 7.5 method planar; beau advise 25 * 20 

building Yes! we have all the information

sun rise and sun set time Yes! running

sun shadowfrequency code Yes! running

grounding face: 1 meter and 10 meter DEM




