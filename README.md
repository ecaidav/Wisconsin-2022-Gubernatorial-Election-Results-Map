# Wisconsin-2022-Gubernatorial-Election-Results-Map

This Jupyter notebook (published via Google Colab) leverages an [OpenElections](https://github.com/openelections) respository with Wisconsin 2022 election data. It uses Python and Pandas to group election results by county and party, specifically for the gubernatorial race. 

It queries the American Community Survey using [autocensus](https://www.census.gov/programs-surveys/acs/data/data-via-api.html) from the U.S. Census Bureau API, extracting county population numbers (which are used in part to determine voter turnout) and demographic insights at the county level, including median family income, educational attainment and poverty level. Data pulled via queries is labeled and merged into the election results DataFrame using Pandas and RegEx.

The election results dataset is visualized as two interactive maps. Each map is developed using a distinct approach--Plotly/Mapbox vs. Altair--but both convey the same insights, albeit in slightly different formats. In both maps, counties are shaded on a blue-red gradient based on the spread of votes awarded to each party's candidate: darker colors indicate a greater marginal victory by the Democratic incumbent, Tony Evers (blue)--or the Republication challenger, Tim Michels (red). Users can hover over the Wisconsin polygons on either map to identify the county name, as well as the party vote breakdown (including point spread between Evers and Michels), voter turnout and several demographic insights about the voting population.

The second map in the notebook was developed by layering charts with Altair. National state and county [TIGER/Line Shapefiles](https://www.census.gov/geographies/mapping-files/time-series/geo/tiger-line-file.html), which are published by the U.S. Census Bureau, are unzipped using Requests and ZipFile. The two census shapefiles, along with the great lakes shapefile published by the [Great Lakes Environmental Research Laboratory (GLERL)](https://github.com/NOAA-GLERL) via GitHub, are read in as GeoDataFrames using GeoPandas. Users can identify the great lakes and counties in states neighboring Wisconsin by hovering over the respective areas on the map.
