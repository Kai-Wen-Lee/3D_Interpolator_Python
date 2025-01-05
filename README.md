# 3D_Interpolator_Python

Jupyter notebook demonstrating use of Dask and Xarray for lightning fast 3-D interpolation of DNS data. <br>
Dask provides parallelism and array chunking, while Xarray provides convienient writing and compression of NETCDF4 files. <br>
Spline interpolation function is translated from IDL by [Swike](https://stackoverflow.com/a/64266640/29046233) from StakedOverflow <br>

Prerequisites: <br>
Python <br>
- Tested on Python 3.11.x
Jupyter Notebook <br>
```
pip install jupyter notebook
```
Dask <br>
```
pip install dask[complete]
```
Xarray <br>
```
pip install xarray
```
NETCDF4-python <br>
```
pip install netcdf4
```

<h1 style="text-align:center;">Please adapt the code to your own needs.</h1>

Due to my needs specifically, the notebook reads coordinate data from: <br>
- course mesh:&emsp;&emsp;&emsp;&emsp;&emsp;(`'geometry_old.nc'`)
- fine mesh:&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;(`'geometry.nc'`)
- course flow field data:&emsp;(`'flowXXXX.nc'`)

and attempts to interpolate data (for instance the temperature field `'temp'`) from the coarse grid to the fine grid. <br>

Arrays are loaded using the `Dask.array.from__array` function to ensure large arrays do not overrun available RAM on system. <br>
Final flowfile is written using `Xarray` with zlib compression (specified in the encoding `dict`)




