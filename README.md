Load necessary libaries
=======================

    library("data.table")
    library("tidyverse")

    ## ── Attaching packages ──────────────────────────────────── tidyverse 1.3.0 ──

    ## ✓ ggplot2 3.3.0     ✓ purrr   0.3.3
    ## ✓ tibble  2.1.3     ✓ dplyr   0.8.5
    ## ✓ tidyr   1.0.2     ✓ stringr 1.4.0
    ## ✓ readr   1.3.1     ✓ forcats 0.4.0

    ## ── Conflicts ─────────────────────────────────────── tidyverse_conflicts() ──
    ## x dplyr::between()   masks data.table::between()
    ## x dplyr::filter()    masks stats::filter()
    ## x dplyr::first()     masks data.table::first()
    ## x dplyr::lag()       masks stats::lag()
    ## x dplyr::last()      masks data.table::last()
    ## x purrr::transpose() masks data.table::transpose()

Load data tables
================

Data was acquired from [Pro Football
Reference](https://www.pro-football-reference.com/).

    for(table_name in c("attend", "coaches", "def", "draft", "off")){
      for(yearr in 2010:2019){
        file_name <- paste0("\"", yearr, table_name, ".csv","\"")
        #tib_name <- paste0(yearr, table_name)
        #assign(table_name, read_csv(file_name))
      }
    }

    #read_csv("2019off.csv")
