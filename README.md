# urban_tree_shade_analysis

Code and materials related to shade model analysis by Dr. John Wilson's team at USC

Storymap URL:https://storymaps.arcgis.com/stories/7f5c570fa0ff4d2eb918f933d869a2d6

Project goals and expected outputs：
Design and implement methods to estimate the shadow surface provided by (a) terrain surfaces (including elevated highways), (b) buildings, and (c) existing tree canopy. The purpose is to conduct the analysis every 10 minutes from sunrise to sunset over a calendar year so that we can use a raster grid to summarize the cumulative hours of shade currently provided by all 6 communities. Dr. John Wilson will specify the methods used and the general characteristics of the data, Yifan Yang will lead the effort to build these methods so we can write papers and improve our description of communities and their greening opportunities.

Manuscript submitted to the journal, describing the methods and values of the output, and the spatiotemporal raster stack we will deploy to further our work, for example, highlighting areas that could be better colored and their ownership status, as well as these candidate sites Whether you currently have a permeable or impermeable surface. These metrics will also be incorporated into the Canopy Scorecard of the Bezos Earth Fund’s work over the next year.

la_sunset_and_sunrise_time.ipynb：
is a notebook-based python file whose function is to call the API to query and output the sunrise and sunset times at a certain point. This file is to query the time from sunrise to sunset every day in Los Angeles in 2023, and divides it every ten minutes; at the same time, we only take integer times here, for example, 6:54 in the morning will become 7:00, in the morning 6:48 will become 6:50. The same time at night is similar, 6:04 pm will become 6:00 pm.


auto_sun_shadowfrequency.ipynb：
completes the entire automation process. You only need to modify the name of the input file to automatically read the sunrise and sunset files. successfully running on the USC SSI PC 007
the code successfully running on the different computer, you can try to run the code named z46 or auto_sun_shadowfrequency, sometimes some pc need to take care SyntaxError: (unicode error) 'unicodeescape' codec can't decode bytes in position 2-3: truncated \UXXXXXXXX escape (<string>, line 33)

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
