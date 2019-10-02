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

* The files are large (62 GB each).  Obtain them from [this Globus endpoint.](https://app.globus.org/file-manager?origin_id=89a33dca-e540-11e9-9bfc-0a19784404f4&origin_path=%2F)
* You will need a Globus endpoint of your own for the transfer.
* Alternatively you may use [Globus Connect Personal.](https://www.globus.org/globus-connect-personal)

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

