# California Wildfires & Their Precursors
#### Solo Project - Breanna Sewell
## Mission
I will be testing for correlation between historical (2013-2020) California wildfire count and expanse (acres burned) and historical weather data, specifically air temperature, precipitation, wind, and land temperature. 

## Resources
California Department of Forestry and Fire Protection (CAL FIRE) 
National Oceanic and Atmospheric Administration (NOAA)
Federal Communications Commission (FCC) Census API

## Obstacles
 - The only common variable between the wildfire dataset and the weather dataset was coordinates, which is a difficult variable to merge. To get around this, I used the FCC API to look up the county for each set of weather coordinates.
 - The weather data had many null values per station. To preserve as much data as possible, I broke each weather variable into its own data frame.
 - Three of the weather variables had insufficient data to analyze once the nulls were dropped: HX01, WSFG, and WSF2. This means I was unable to analyze land temperature and wind speed.
 - After merging the first two data frames, wildfire extent and DX90, many rows dropped. This was because many fires span multiple counties, which hadn’t occurred to me previously. This is problematic not only because of the loss of data, but because of the type of data lost. Generally speaking, fires that span multiple counties are the largest fires – which are critical data points. I had to conduct my analysis at the state level instead of county level.

## Findings
There is far less correlation between the weather and wildfire variables than expected. In most cases, there was little to no correlation. In a couple instances, there was a moderate correlation.

Relationships were analyzed between the following variables:
 - Wildfire extent – acres burned
 - Wildfire duration – number of days fire lasted
 - DX90 – number of days over 90˚F
 - EMXP – extreme maximum daily precipitation (in.)
 - EMXT – extreme maximum daily temperature (˚F)
 - PRCP – total annual precipitation (in.)
 - TAVG – average annual temperature (˚F)
 - TMAX – average annual maximum temperature (˚F)

The r-value and correlation strength of each analysis are listed below:
 - DX90 vs. fire extent: 0.58, moderate
 - DX90 vs. fire duration: 0.15, none
 - EMXP vs. fire extent: -0.47, weak
 - EMXP vs. fire duration: 0.39, weak
 - EMXT vs. fire extent: 0.43, weak
 - EMXT vs. fire duration: 0.43, weak
 - PRCP vs. fire extent: -0.29, weak
 - PRCP vs. fire duration: 0.44, weak
 - TAVG vs. fire extent: 0.22, none
 - TAVG vs. fire duration: 0.04 none
 - TMAX vs. fire extent: 0.17, none
 - TMAX vs. fire duration: 0.19, none

## Improvements
 - Improved granularity of data – wildfire damage and duration at the county or city level versus at the state level
 - Visual data – heat map showing relationship between weather and fire
 - Additional statistical tests and manipulation of data
 - Additional years of data – ideally back to 1990
