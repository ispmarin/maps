# Maps in Python

I'm investigating the possible solutions for mapping in Python. The requirements are:

- Plot several different elements (points, markers, lines, polylines, polygons)
- I need to plot maps with variable resolution (from scale from 1:10 to 1:100.000)
- A tiles provider (OpenStreetMap or other)
- The plots should be generated offline
- A good interface with pandas 
- Map interaction with time variable

Interesting discussion:

- https://news.ycombinator.com/item?id=6604785
- http://sensitivecities.com/so-youd-like-to-make-a-map-using-python-EN.html

## Folium
[Folium](https://github.com/python-visualization/folium/) is a Python interface for the [Leaflet](https://github.com/Leaflet/Leaflet) Javascript map library. 

- Still an early project (version 0.1.6 or 0.2.0-dev)
- The default tile provider is OpenStreetMap
- There is no [offline](https://github.com/python-visualization/folium/issues/351) option for the moment (every redraw calls the tile API)
- Supports markers, points, lines, polylines and floaters
- Can scale, depending only on the tiles available
- Has a nice gallery with jupyter notebooks as [examples](http://nbviewer.jupyter.org/github/ocefpaf/folium_notebooks/tree/master/)

## Plotly
[Plotly](https://github.com/plotly/plotly.py) was a closed source, server-based general plotting library that has been open sourced recently.

- A more mature project
- Can do several kinds of visualizations
- Is able to plot offline
- Supports markers, points, lines
- [Cannot scale](https://github.com/plotly/plotly.js/issues/249) the underlying tiles


## Basemap
[Basemap](https://github.com/matplotlib/basemap/) is a [Matplotlib](https://github.com/matplotlib/) extension for mapping and cartography.

- Is based on matplotlib, so again, if you are familiar with Matplotlib is quite easy to adapt
- Is static, no interactivity
- Kinda complicated to install (no pip package easily available)
- Can scale and has high resolution maps
- Very flexible with cartographic settings
- Probably will not be maintained in the [long term](https://github.com/matplotlib/basemap/issues/191) (Cartopy is suggested as a possible replacement)

## Cartopy
[Cartopy](https://github.com/SciTools/cartopy) is a static cartographic library based on Matplotlib. 

- Needs shapely < 1.5.12, otherwise fails
- Static maps, no interaction
- Can use several tile providers or no tiles at all
- Can read shapefiles
- Uses shapely
- Matplotlib integration makes easier to use (if you know matplotlib, that is)
- Supports markers, points, lines, polylines
- Can cache the tiles and maps, plots are static by default

## But why not use <insert technology here>?
Several plotting tools are using a Javascript backend to do the plotting, like Plotly and Folium. Why not use directly Javascript? So far, the main reason is that our stack is mostly Python and the platforms where the data is coming from is messy. Python is the glue that we use to hide the several backend data sources, so having Python is a reasonable choice for now. 
