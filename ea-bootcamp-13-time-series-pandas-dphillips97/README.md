## Precipitation and Stream Discharge For Boulder Creek, Boulder, CO

### Implement a time series data workflow in a new Jupyter Notebook to create the following figures that highlight the 2013 flood:

* **Figure 1: Precipitation (inches)**
    * one subplot for daily precipitation values from Aug 1, 2013 to Oct 1, 2013
        * there should be one value for each day in time period
        * x axis label should be month-day (e.g. "Aug-01")
    * one subplot for monthly maximum values of precipitation in 2013
        * there should be one value for each month in 2013
        * x axis label should be month-day (e.g. "Aug-01")
    * one subplot for monthly totals of precipitation for all years in dataset
        * there should be one value for each month-year (e.g. Jan 2001, Feb 2001, so on)
        * * x axis label should be Year (e.g. "2013")
        
* **Figure 2: Stream Discharge (cubic feet per second - CFS)**
    * one subplot for daily discharge values from Aug 1, 2013 to Oct 1, 2013
        * there should be one value for each day in time period
        * x axis label should be month-day (e.g. "Aug-01")
    * one subplot for monthly maximum values of discharge in 2013
        * there should be one value for each month in 2013
        * x axis label should be month-day (e.g. "Aug-01")
    * one subplot for monthly totals of discharge for all years in dataset
        * there should be one value for each month-year (e.g. Jan 2001, Feb 2001, so on)
        * x axis label should be Year (e.g. "2013")

You may choose any color, style, etc, but be sure to make selections that appropriately display the values. For example, you can play around with scatter vs line plots, plot backgrounds, etc. 

For all plots, be sure to include appropriate titles and axes labels including units of measurement where appropriate. 

**After the figure code in your notebook, include a final Markdown cell with text to describe what can be learned about the 2013 flood from the figures (e.g. daily, monthly and yearly comparisons).**   


### Use the following data collected for Boulder Creek, Boulder, CO:

* Download the EarthPy data package called `colorado-flood`: 
    * `805333-precip-daily-1948-2013.csv` in the `precipitation` subdirectory
        * Daily total precipitation in inches between 1948 and 2013
        * "no data" value is 999.99
        * [Original datasource from National Oceanic and Atmospheric Administration (NOAA)](https://www.ncdc.noaa.gov/cdo-web/search)
    * `06730200-discharge-daily-1986-2013.csv` in the `discharge` subdirectory
        * Daily mean stream discharge in cubic feet per second (CFS) between 1986-2013 
        * Dataset does not have a value for "no data"
        * [Original datasource from U.S. Geological Survey (USGS)](http://waterdata.usgs.gov/nwis/dv?cb_00060=on&format=html&site_no=06730200&referred_module=sw&period=&begin_date=1986-10-01&end_date=2013-12-31)


### Organize your notebook using best practices for Python and Jupyter Notebook:

* Include an overview Markdown cell at top of notebook with a title and short description of the workflow
* General outline for code:
    * Begin with imports
    * Followed by function definitions (when needed)
    * Followed by setting working directory
    * Followed by all other code needed for workflow
* Use code that is reproducible across different computers (e.g. paths, 
* Follow PEP 8 guidelines for line lengths, white space, etc to support readibility
* Include comments throughout the notebook 
* Use Markdown cells to provide longer text (i.e. interpretation of plots, longer descriptions of workflow)

This assignment is meant for you to practice on designing workflows on your own. Aim to use concise and efficient code as needed, but you are not required to use functions, loops, or conditional statements for this assignment. Focus on getting a workflow completed first, then on improving efficiency and readiblity of your code.

### How To Get Started

You will create a new Jupyter Notebook for this assignment and populate it with your organized code per the guidelines provided above. You will `git add`, `commit` and `push` this new Jupyter Notebook to your fork of the repository for assignment 13 (e.g. eastudent/ea-bootcamp-13-time-series-pandas-eastudent) and submit a pull request to the original repository owned by earthlab-education. 

Conceptually, it can help to begin with:
* a review of each CSV file to look at the contents: 
   * which column contains the date?
   * which column contains the measured value?
* a sketch of each figure.  
    * What does each subplot look like?
* an outline of the steps you need to create each data component that is needed for each subplot. 
    * How can you create each data component that is needed:
        * daily values for Aug-Oct 2013
        * monthly maximums for 2013
        * monthly totals for all years in dataset
