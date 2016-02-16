Title: 
Date: 
Category: 
Modified: 
Tags: 
Slug: 
Authors: 
Summary: 

First install cython and numpy on cartopy 0.13 because failure. Then install libproj-dev e libgdal-dev e libgeos-dev. Depois 

export CPLUS_INCLUDE_PATH=/usr/include/gdal

export C_INCLUDE_PATH=/usr/include/gdal


e aí 

pip install gdal==1.10

só então pode instalar pip install "cartopy[plotting]".
