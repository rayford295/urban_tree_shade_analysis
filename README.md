# urban_tree_shade_analysis
Code and materials related to shade model analysis by Dr. John Wilson's team at USC

Session 1, sunrise and sunset times

Sunrise_Sunset_2023_LA：
A file containing the sunrise and sunset time points for Los Angeles throughout the year 2023. The same times are processed into integers.

Sunrise_Sunset_Intervals_2023_LA：
A file containing the sunrise and sunset time points of Los Angeles throughout 2023, and each day is a sheet. There are 365 sheets in total, and they are also divided every 10 minutes. Times are treated as integers.

la_sunset_and_sunrise_time.ipynb：
is a notebook-based python file whose function is to call the API to query and output the sunrise and sunset times at a certain point. This file is to query the time from sunrise to sunset every day in Los Angeles in 2023, and divides it every ten minutes; at the same time, we only take integer times here, for example, 6:54 in the morning will become 7:00, in the morning 6:48 will become 6:50. The same time at night is similar, 6:04 pm will become 6:00 pm.
