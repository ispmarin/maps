# Maps in Python

I'm investigating the possible solutions for mapping in Python. The requirements are:

- Plot several different elements (points, markers, lines, polylines, polygons)
- I need to plot maps with variable resolution (from scale from 1:10 to 1:100.000)
- A tiles provider (OpenStreetMap or other)
- The plots should be generated offline
- A good interface with pandas 
- Map interaction with time variable

## Folium
[Folium](https://github.com/python-visualization/folium/) is a Python interface for the [Leaflet](https://github.com/Leaflet/Leaflet) Javascript map library. 

- Still an early project (version 0.1.6 or 0.2.0-dev)
- The default tile provider is OpenStreetMap
- There is no [offline](https://github.com/python-visualization/folium/issues/351) option for the moment (every redraw calls the tile API)
- Supports markers, points, lines, polylines and floaters
- Can scale, depending only on the tiles available

## Plotly
[Plotly](https://github.com/plotly/plotly.py) was a closed source, server-based general plotting library that has been open sourced recently.

- A more mature project
- Can do several kinds of visualizations
- Is able to plot offline
- Supports markers, points, lines
- [Cannot scale](https://github.com/plotly/plotly.js/issues/249) the underlying tiles

So plotly is a no go.

## Basemap
TODO

