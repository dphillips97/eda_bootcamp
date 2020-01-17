## Final Project for Earth Analytics Bootcamp

Create a new notebook called `ea-bootcamp-final-project.ipynb` for a final report with two figures:
1. precipitation patterns of Boulder, CO and San Francisco, CA.
2. stream discharge for the 2013 Colorado floods for four sites across Colorado. 

Requirements for the notebook and for each figure are provided below. 


## Overall Report Requirements 

* Include an overview Markdown cell with a title and short description of the structure of the notebook and the workflows. 
    * In each workflow description, identify the original data sources for the data used in the notebook. 
* After each figure, include a Markdown cell with text to describe the figure and what it tell you about the phenomenon of interest. 

Remember to follow best practices for outlining code and for readability and reproducibility in your notebook:
* Employ the standard Python code outline:  
    * Begin with imports.
    * Followed by function definitions.
    * Followed by setting working directory (as needed).
    * Followed by all other code needed for workflow.
      * In this portion of the code, you can use Markdown cells to identify different sections of the code (e.g. a section for Precipitation Patterns of Boulder, CO and San Francisco, CA).
* Use DRY code and other strategies for readability and reproducibility:
    * Reduce your code wherever possible - use the outputs of selections and functions as the inputs to other functions, plot inputs, etc. Balance combining code with readbility to ensure that the workflow is clear and easy to follow.
    * Use code that is reproducible across different computers (e.g. paths) as needed.
    * Follow PEP 8 guidelines for line lengths, white space, etc, to support readibility.
    * Include comments throughout the notebook.
    * Use Markdown cells to provide longer text (i.e. interpretation of plots, longer descriptions of workflow).


## Figure 1: Precipitation Patterns of Boulder, CO and San Francisco, CA 

Create a figure with two subplots:
* One subplot displaying the **Monthly Median Precipitation Values (inches) for 1989 to 2018** for both cities (i.e. both cities on one plot).
* One subplot displaying the **Annual Maximum Precipitation Values (inches) for 1989 to 2018** for both cities (i.e. both cities on one plot).
    * Include a legend for each subplot.
    * Use different colors, line styles, etc to highlight each site (i.e. each city should be a unique color/style that is used again across the plots). 
    * For each plot, be sure to include appropriate titles and axes labels including units of measurement where appropriate.


### Other Code Requirements

* Write a function that downloads (using earthpy) and imports the data into numpy arrays.
* Write a function that can calculate either median or maximum values for either all months or all years of an array and converts the units from millimeters to inches.  
* Use a loop to download/import the data.
* Use a loop to calculate the monthly median and yearly maximum precipitation values in inches between 1989 to 2018 for both cities. 


### Precipitation Data

* boulder-monthly-precip-mm-1948-2018.csv from https://ndownloader.figshare.com/files/20026409
    * The dataset contains the total monthly precipitation (millimeters) for each month and year for Boulder, CO between 1948 and 2018. The data are organized with a row for each for each year (in order from 1948 to 2018) and one column for month (in order from January to December). This file does not contain headers. 
    * Original data from <a href="https://www.esrl.noaa.gov/psd/boulder/Boulder.mm.precip.html" target="_blank">U.S. National Oceanic and Atmospheric Administration (NOAA)</a>.
* san-franscisco-monthly-precip-mm-1948-2018.csv from https://ndownloader.figshare.com/files/20026412
    * The dataset contains the total monthly precipitation (millimeters) for each month and year for San Francisco, CA between 1948 and 2018. The data are organized with a row for each for each year (in order from 1948 to 2018) and one column for month (in order from January to December). This file does not contain headers. 
    * Original data from <a href="https://w2.weather.gov/climate/xmacis.php?wfo=mtr" target="_blank">National Weather Service</a>       


### Helpful Tips

* Build your code incrementally: complete the workflow first without functions or loops to ensure that you have the components needed for the workflow. 
   * Before writing a function, write the code that is needed to complete the tasks (e.g. download and import data) for one city. Then, write your function to combine those steps and test your function on that same city. 
   * Once your function is working successfully on one city, write loop to run your function for all cities.
* You can use `np.set_printoptions(suppress=True)` to suppress scientific notation in numpy arrays.
* You can use `np.arange()` to create a numpy array with consecutive values using a start and end value.
* You can use `plt.tight_layout()` (and play with the figsize) in your plot code to have matplotlib automatically space the subplots evenly within a figure. 


## Figure 2: Stream Discharge For 2013 Colorado Floods

Create a figure with two subplots:
* One subplot displaying the **Daily Mean Discharge** (cubic feet per second, CFS) for **Aug - Oct 2013** for all four sites (i.e. all sites on one plot).
* One subplot displaying the **Annual Maximum of Mean Discharge** (cubic feet per second, CFS) for **1990-2018** for all four sites (i.e. all sites on one plot).
    * Include a legend for each subplot.
    * Use different colors, line styles, etc to highlight each site (i.e. each site should be a unique color/style that is used again across the plots). 
    * For each plot, be sure to include appropriate titles and axes labels including units of measurement where appropriate.
    * DRY Code: include selections, resamples, etc, directly in the plot code, to remove the need for intermediary dataframes created from selections, resamples, etc. 


### Other Code Requirements

* Write a function that combines the `hydrofunctions` tasks needed to create a pandas dataframe from the downloaded data.
    * in your function, rename the columns in the dataframe to more descriptive names (e.g. discharge and flag)
* Use a loop to apply your function to each of the four sites (i.e. use a loop to create the dataframe for each site).


### Stream Discharge Data

For this section of the report, you will use the `hydrofunctions` package in your conda environment to programmatically download stream discharge data for **January 1, 1990 through December 31, 2018 for four U.S. Geological Survey (USGS) stream gages across Colorado**:
1. site `06730500` for the [Boulder Creek Station near Longmont, CO](https://waterdata.usgs.gov/nwis/inventory/?site_no=06730500) in Weld County (Northern Colorado)
2. site `09105000` for the [Plateau Creek Station near Cameo, CO](https://waterdata.usgs.gov/nwis/inventory/?site_no=09105000) in Mesa County (Western Colorado)
3. site `07106300` for the [Fountain Creek Station near Pinon, CO](https://waterdata.usgs.gov/nwis/inventory/?site_no=07106300) in Pueblo County (Central Colorado)
4. site `07126390` for the [Lockwood Canyon Creek Station near Thatcher, CO](https://waterdata.usgs.gov/co/nwis/inventory/?site_no=07126390) in Las Animas County (Southeastern Colorado)

The [documentation for hydrofunctions package](https://hydrofunctions.readthedocs.io/en/master/usage.html) provides instructions and examples for using functions in this package to download data directly from the USGS National Water Information System (NWIS) and create a pandas dataframe. 

The dataframe created by the hydrofunctions functions will include the following:
* Daily mean stream discharge in cubic feet per second (CFS) in column called `USGS:` plus site info (e.g. `USGS:06730500:00060:00003`) 
* An indicator (or flag) of quality of measurement in column called called `USGS:` plus site info and `_qualifiers`(e.g. `USGS:06730500:00060:00003_qualifiers`)
* "No data" values already addressed by hydrofunctions

### Helpful Tips

* Build your code incrementally: complete the workflow first without functions or loops to ensure that you have the components needed for the workflow. 
   * Start with the `hydrofunction` functions and get those steps working successfully to create a dataframe for one site. Then, write your function to combine those steps and test your function on that same site. 
   * Once your function is working successfully on one site, write loop to run your function for all sites.
* You can use `plt.tight_layout()` (and play with the figsize) in your plot code to have matplotlib automatically space the subplots evenly within a figure. 
* To provide interpretation of the stream discharge plots, it can help to review a [map of Colorado counties](https://geology.com/county-map/colorado.shtml) as well as the wikipedia entries on the [2013 Colorado Floods](https://en.wikipedia.org/wiki/2013_Colorado_floods) and other events that have occurred at [Fountain Creek](https://en.wikipedia.org/wiki/Fountain_Creek_(Arkansas_River_tributary)). 
