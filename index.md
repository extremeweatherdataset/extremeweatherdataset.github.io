# The ExtremeWeather Dataset

### About the Data

The data is available as one HDF5 file per year, which are formatted like so: “climo\_yyyy.h5”, like “climo_1979.h5”.

 Each HDF5 file contains two datasets:
  
*  “images”
*  “boxes”

Here is a snippet of code to load the datasets with the python library, [h5py](http://docs.h5py.org/en/latest/build.html#python-distributions):


```python
import h5py
data_path = "./climo_1979.h5"
h5f = h5py.File(data_path)
images = h5f["images"] # (1460,16,768,1152) numpy array
boxes = h5f["boxes"] # (1460,15,5) numpy array
```

The two variables, "images" and "boxes" are described below:

#### images

![](./variables.jpg)

*   a (1460,16,768,1152) array
*   1460 example images (4 per day, 365 days in the year)
*   16 channels in each image corresponding to the [following variables](#variables)
*   each channel is 768 x 1152 corresponding to one measurement per 25 square km on earth

#### boxes

*   a (1460,15,5) array
*   1460 examples (4 per day, 365 days in the year)
*   15 rows (rows without boxes for that example are filled with -1's)
*   each row has 5 elements:

    *   4 bounding box coordinates + the class
    *   ymin, xmin, ymax, xmax, class
    *   y corresponds to the size 768 dimension and the vertical axis when plotted
    *   x corresponds to the size 1152 dimension and horizontal a
    *   classes are types of extreme weather events and go from 0 to 3:

        **0**. Tropical Depression

        **1**. Tropical Cyclone

        **2**. Extratropical Cyclone

        **3**. Atmospheric River

### Download

<a name="download"></a>

*   1979: [climo_1979.h5](http://portal.nersc.gov/project/dasrepo/DO_NOT_REMOVE/extremeweather_dataset/h5data/climo_1979.h5) (62 GB)
*   1980: [climo_1980.h5](http://portal.nersc.gov/project/dasrepo/DO_NOT_REMOVE/extremeweather_dataset/h5data/climo_1980.h5) (62 GB)
*   1981: [climo_1981.h5](http://portal.nersc.gov/project/dasrepo/DO_NOT_REMOVE/extremeweather_dataset/h5data/climo_1981.h5) (62 GB)
*   1982: [climo_1982.h5](http://portal.nersc.gov/project/dasrepo/DO_NOT_REMOVE/extremeweather_dataset/h5data/climo_1982.h5) (62 GB)

*   1984: [climo_1984.h5](http://portal.nersc.gov/project/dasrepo/DO_NOT_REMOVE/extremeweather_dataset/h5data/climo_1984.h5) (62 GB)
*   1985: [climo_1985.h5](http://portal.nersc.gov/project/dasrepo/DO_NOT_REMOVE/extremeweather_dataset/h5data/climo_1985.h5) (62 GB)
*   1986: [climo_1986.h5](http://portal.nersc.gov/project/dasrepo/DO_NOT_REMOVE/extremeweather_dataset/h5data/climo_1986.h5) (62 GB)
*   1987: [climo_1987.h5](http://portal.nersc.gov/project/dasrepo/DO_NOT_REMOVE/extremeweather_dataset/h5data/climo_1987.h5) (62 GB)
*   1988: [climo_1988.h5](http://portal.nersc.gov/project/dasrepo/DO_NOT_REMOVE/extremeweather_dataset/h5data/climo_1988.h5) (62 GB)
*   1989: [climo_1989.h5](http://portal.nersc.gov/project/dasrepo/DO_NOT_REMOVE/extremeweather_dataset/h5data/climo_1989.h5) (62 GB)
*   1990: [climo_1990.h5](http://portal.nersc.gov/project/dasrepo/DO_NOT_REMOVE/extremeweather_dataset/h5data/climo_1990.h5) (62 GB)
*   1991: [climo_1991.h5](http://portal.nersc.gov/project/dasrepo/DO_NOT_REMOVE/extremeweather_dataset/h5data/climo_1991.h5) (62 GB)
*   1992: [climo_1992.h5](http://portal.nersc.gov/project/dasrepo/DO_NOT_REMOVE/extremeweather_dataset/h5data/climo_1992.h5) (62 GB)
*   1993: [climo_1993.h5](http://portal.nersc.gov/project/dasrepo/DO_NOT_REMOVE/extremeweather_dataset/h5data/climo_1993.h5) (62 GB)
*   1994: [climo_1994.h5](http://portal.nersc.gov/project/dasrepo/DO_NOT_REMOVE/extremeweather_dataset/h5data/climo_1994.h5) (62 GB)
*   1995: [climo_1995.h5](http://portal.nersc.gov/project/dasrepo/DO_NOT_REMOVE/extremeweather_dataset/h5data/climo_1995.h5) (62 GB)
*   1996: [climo_1996.h5](http://portal.nersc.gov/project/dasrepo/DO_NOT_REMOVE/extremeweather_dataset/h5data/climo_1996.h5) (62 GB)
*   1997: [climo_1997.h5](http://portal.nersc.gov/project/dasrepo/DO_NOT_REMOVE/extremeweather_dataset/h5data/climo_1997.h5) (62 GB)
*   1998: [climo_1998.h5](http://portal.nersc.gov/project/dasrepo/DO_NOT_REMOVE/extremeweather_dataset/h5data/climo_1998.h5) (62 GB)

*   2000: [climo_2000.h5](http://portal.nersc.gov/project/dasrepo/DO_NOT_REMOVE/extremeweather_dataset/h5data/climo_2000.h5) (62 GB)
*   2001: [climo_2001.h5](http://portal.nersc.gov/project/dasrepo/DO_NOT_REMOVE/extremeweather_dataset/h5data/climo_2001.h5) (62 GB)
*   2002: [climo_2002.h5](http://portal.nersc.gov/project/dasrepo/DO_NOT_REMOVE/extremeweather_dataset/h5data/climo_2002.h5) (62 GB)
*   2003: [climo_2003.h5](http://portal.nersc.gov/project/dasrepo/DO_NOT_REMOVE/extremeweather_dataset/h5data/climo_2003.h5) (62 GB)
*   2004: [climo_2004.h5](http://portal.nersc.gov/project/dasrepo/DO_NOT_REMOVE/extremeweather_dataset/h5data/climo_2004.h5) (62 GB)
*   2005: [climo_2005.h5](http://portal.nersc.gov/project/dasrepo/DO_NOT_REMOVE/extremeweather_dataset/h5data/climo_2005.h5) (62 GB)

### Additional Info

<a name="variables"></a>

#### Variable Values:


The variables are the 2nd dimension of the "images" dataset in the HDF5 in the following order:

**0**. _PRECT_

*	**Total (convective and large-scale) precipitation rate (liq + ice)**

**1**. _PS_

* **Surface Pressure**

**2**. _PSL_

* 	**Sea level pressure**

**3**. _QREFHT_

* **Reference height humidity** 

**4**. _T200_

* **Temperature at 200 mbar pressure surface** 

**5**. _T500_

* **Temperature at 500 mbar pressure surface**

**6**. _TMQ_

* **Total (vertically integrated) precipitatable water**

**7**. _TREFHT_

* **Reference height temperature**

**8**. _TS_

* **Surface temperature (radiative)**

**9**. _U850_

* **Zonal wind at 850 mbar pressure surface**

**10**. _UBOT_

* **Lowest model level zonal wind**

**11**. _V850_

* **Meridional wind at 850 mbar pressure surface**

**12**. _VBOT_

* **Lowest model level meridional wind**

**13**. _Z100_

* **Geopotential Z at 100 mbar pressure surface**

**14**. _Z200_

* **Geopotential Z at 200 mbar pressure surface**

**15**. _ZBOT_

* **Lowest model level height**

More information as to what each variable means is available [here](http://www.cesm.ucar.edu/models/cesm1.0/cam/docs/ug5_0/hist_flds_fv_cam5.html)


### Using the Data in Your Paper

To use this data in a paper please cite this paper:

[ExtremeWeather: A large-scale climate dataset for semi-supervised detection, localization, and understanding of extreme weather events](https://papers.nips.cc/paper/6932-extremeweather-a-large-scale-climate-dataset-for-semi-supervised-detection-localization-and-understanding-of-extreme-weather-events), Racah et al., 2017.

[bibtex link](./extremeweather-a-large-scale-climate-dataset-for-semi-supervised-detection-localization-and-understanding-of-extreme-weather-events.bib)

