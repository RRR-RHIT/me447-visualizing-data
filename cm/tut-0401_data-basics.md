
data basics
-----------

After working through this tutorial, you should be able to

-   Describe a "tidy" dataset
-   Read data from an Excel file
-   Read and write CSV data files
-   Access data sets included with R and R packages

preparation
-----------

Launch your RStudio project for the course, *me447-visualizing-data.Rproj*.

Packages

-   Install *tidyverse*
-   Install *readxl*

The tidyverse is a set of packages that includes: ggplot2 (for data visualization), dplyr (for data manipulation), tidyr (for data tidying), and readr (for data import).

Data

-   Manually download *pressure-calibration.xlsx* file from the *data* folder on our website.
-   Save the file to your *data* directory in your course folder.

Script

-   Open a new R file *tut03\_data-basics.R*
-   Save it to your *practiceR* folder

Start with a header

    #  ------------------------------------------
    #  data basics
    #
    #  your name
    #  date
    #  ------------------------------------------

Initialize

    # if you like to start with an empty workspace
    rm(list = (ls()))

    # libraries we use in this tutorial
    library(tidyverse)
    library(readxl)

Next tutorial: [read data from an Excel file](tut-0402_read-excel.md)

------------------------------------------------------------------------

[main page](../README.md)<br> [topics page](../README-by-topic.md)