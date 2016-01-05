

## Problem: We're at GISS, data on discover
### Solution: iPython (Jupyter) Notebooks
* iPython prompt as primary tool for data exploration/analysis.
* Replaces bash as user interface
* Everything in one consistent framework: no more Fortran + Perl + NCO + Python + bash scripting  

###Examples:
* [IPyhton interact and widgets... (3-line ncview)](http://earthpy.org/pyncview_pm.html)
* [Optimizing code for iso-surfaces...](https://ocefpaf.github.io/python4oceanographers/blog/2015/10/05/isosurfaces)
* [Estimated likelihood of observing...](http://nbviewer.ipython.org/github/cossatot/lanf_earthquake_likelihood/blob/master/notebooks/lanf_manuscript_notebook.ipynb)

###Work:
* Two days to get Jupyter on 
discover in conformance with NASA security 
regulations.

---------------------------------

##Problem: Pre-process, post-process data files
###Solution: Python + netCDF

* More flexible, less arcane than NCO
  - Most useful for generating complex input/data files
* Faster to write than Fortran

```
import netCDF4
nc = netCDF4.Dataset('input_datafile.nc')
C = nc.variables['A'][:] + nc.variables['B'][:]
nco = netCDF4.Dataset('output_datafile.nc', 'w')
nco.createDimension('jm', len(nc.dimensions['jm']))
nco.createDimension('im', len(nc.dimensions['im']))
nco.createVariable('C', 'd', ('jm', 'im'))
nco.close()
nc.close()
```
-----------------------------------------------

##Problem: Uniform Data Access
Consider plot program (like Panoply) that plots stuff in a netCDF file.
Now we want to:
* Plot combinations of variables in the file
* Compute on data, not just plot it!

###Solution:
* Abstract data access away from particular format (netCDF file)
* xray: Carry metadata with numpy variables, useful for plotting and other programs
* Expression Language: Compute expressions of data on-the-fly

###Example:
```
ds1 = open_dataset('single_month_file.nc')
ds2 = open_dataset('multi_month_file.nc')(month=5)
ds3 = join_dataset(
    (ds1, ds2),
    formulae={ 'C' : 'ds1.A + ds2.B' })
C = ds3.variables['C']
```

###Work:
* Careful design needed to get it right.
* More design than coding.
* Antecedents exist, but they are proprietary.

-------------------------------------------------------------------

## Problem: Mining GCM Output
###Solution: Pandas + ggplot

[ggplot for Python](http://pt.slideshare.net/PyData/ggplotforpython1-140503092932phpapp02)
Book: [The Grammar of Graphics](https://clio.columbia.edu/catalog/7899682?counter=1)

![Facets](http://image.slidesharecdn.com/ggplotforpython1-140503092932-phpapp02-140530155200-phpapp02/95/ggplot-for-python-sv-2014-13-638.jpg?cb=1402317710)

![Matplotlib vs. Python](http://image.slidesharecdn.com/ggplotforpython1-140503092932-phpapp02-140530155200-phpapp02/95/ggplot-for-python-sv-2014-14-638.jpg?cb=1402317710)

-----------------------------------------------------------

## Problem: Arrays Bigger than Memory!
###Solution: dask

[Calculations with arrays bigger than your memory (dask arrays)](http://earthpy.org/dask.html)

-----------------------------------------------------

##Problem: Make maps
###Solution: matplotlib/basemap

![Basemap Example](http://matplotlib.org/basemap/_images/plotetopo5_00_00.png)

###Work:
* "Plotters" needed to abstract away different grids and data formats:
  - Lat/Lon Grid
  - Cube Sphere Grid
  - Elevation Grid (Ice Modling)
  - Local Grids (Ice Modeling)

-----------------------------------------------
##Problem: Integrate Legacy Code


##
