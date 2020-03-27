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

    name_key <- read_csv("names.csv")

    ## Parsed with column specification:
    ## cols(
    ##   full_name = col_character(),
    ##   abbr_name = col_character()
    ## )

    for(table_name in c("attend", "coaches", "def", "draft", "off")){
      for(yearr in 2010:2019){
        file_name <- paste0(yearr, table_name, ".csv")
        tib_name <- paste0(table_name, yearr)
        assign(tib_name, read_csv(file_name))
      }
    }

    ## Parsed with column specification:
    ## cols(
    ##   .default = col_number(),
    ##   Tm = col_character(),
    ##   Year = col_double(),
    ##   `Week 4` = col_character(),
    ##   `Week 5` = col_character(),
    ##   `Week 6` = col_character(),
    ##   `Week 7` = col_character(),
    ##   `Week 8` = col_character(),
    ##   `Week 9` = col_character(),
    ##   `Week 10` = col_character()
    ## )

    ## See spec(...) for full column specifications.

    ## Parsed with column specification:
    ## cols(
    ##   .default = col_number(),
    ##   Tm = col_character(),
    ##   Year = col_double(),
    ##   `Week 5` = col_character(),
    ##   `Week 6` = col_character(),
    ##   `Week 7` = col_character(),
    ##   `Week 8` = col_character(),
    ##   `Week 9` = col_character(),
    ##   `Week 11` = col_character()
    ## )

    ## See spec(...) for full column specifications.

    ## Parsed with column specification:
    ## cols(
    ##   .default = col_number(),
    ##   Tm = col_character(),
    ##   Year = col_double(),
    ##   `Week 4` = col_character(),
    ##   `Week 5` = col_character(),
    ##   `Week 6` = col_character(),
    ##   `Week 7` = col_character(),
    ##   `Week 8` = col_character(),
    ##   `Week 9` = col_character(),
    ##   `Week 10` = col_character(),
    ##   `Week 11` = col_character()
    ## )

    ## See spec(...) for full column specifications.

    ## Parsed with column specification:
    ## cols(
    ##   .default = col_number(),
    ##   Tm = col_character(),
    ##   Year = col_double(),
    ##   `Week 4` = col_character(),
    ##   `Week 5` = col_character(),
    ##   `Week 6` = col_character(),
    ##   `Week 7` = col_character(),
    ##   `Week 8` = col_character(),
    ##   `Week 9` = col_character(),
    ##   `Week 10` = col_character(),
    ##   `Week 11` = col_character(),
    ##   `Week 12` = col_character()
    ## )

    ## See spec(...) for full column specifications.

    ## Parsed with column specification:
    ## cols(
    ##   .default = col_number(),
    ##   Tm = col_character(),
    ##   Year = col_double(),
    ##   `Week 4` = col_character(),
    ##   `Week 5` = col_character(),
    ##   `Week 6` = col_character(),
    ##   `Week 7` = col_character(),
    ##   `Week 8` = col_character(),
    ##   `Week 9` = col_character(),
    ##   `Week 10` = col_character(),
    ##   `Week 11` = col_character(),
    ##   `Week 12` = col_character()
    ## )

    ## See spec(...) for full column specifications.

    ## Parsed with column specification:
    ## cols(
    ##   .default = col_number(),
    ##   Tm = col_character(),
    ##   Year = col_double(),
    ##   `Week 4` = col_character(),
    ##   `Week 5` = col_character(),
    ##   `Week 6` = col_character(),
    ##   `Week 7` = col_character(),
    ##   `Week 8` = col_character(),
    ##   `Week 9` = col_character(),
    ##   `Week 10` = col_character(),
    ##   `Week 11` = col_character()
    ## )

    ## See spec(...) for full column specifications.

    ## Parsed with column specification:
    ## cols(
    ##   .default = col_number(),
    ##   Tm = col_character(),
    ##   Year = col_double(),
    ##   `Week 4` = col_character(),
    ##   `Week 5` = col_character(),
    ##   `Week 6` = col_character(),
    ##   `Week 7` = col_character(),
    ##   `Week 8` = col_character(),
    ##   `Week 9` = col_character(),
    ##   `Week 10` = col_character(),
    ##   `Week 11` = col_character(),
    ##   `Week 13` = col_character()
    ## )

    ## See spec(...) for full column specifications.

    ## Parsed with column specification:
    ## cols(
    ##   .default = col_number(),
    ##   Tm = col_character(),
    ##   Year = col_double(),
    ##   `Week 1` = col_character(),
    ##   `Week 5` = col_character(),
    ##   `Week 6` = col_character(),
    ##   `Week 7` = col_character(),
    ##   `Week 8` = col_character(),
    ##   `Week 9` = col_character(),
    ##   `Week 10` = col_character(),
    ##   `Week 11` = col_character()
    ## )

    ## See spec(...) for full column specifications.

    ## Parsed with column specification:
    ## cols(
    ##   .default = col_number(),
    ##   Tm = col_character(),
    ##   Year = col_double(),
    ##   `Week 4` = col_character(),
    ##   `Week 5` = col_character(),
    ##   `Week 6` = col_character(),
    ##   `Week 7` = col_character(),
    ##   `Week 8` = col_character(),
    ##   `Week 9` = col_character(),
    ##   `Week 10` = col_character(),
    ##   `Week 11` = col_character(),
    ##   `Week 12` = col_character()
    ## )

    ## See spec(...) for full column specifications.

    ## Parsed with column specification:
    ## cols(
    ##   .default = col_number(),
    ##   Tm = col_character(),
    ##   Year = col_double(),
    ##   `Week 4` = col_character(),
    ##   `Week 5` = col_character(),
    ##   `Week 6` = col_character(),
    ##   `Week 7` = col_character(),
    ##   `Week 8` = col_character(),
    ##   `Week 9` = col_character(),
    ##   `Week 10` = col_character(),
    ##   `Week 11` = col_character(),
    ##   `Week 12` = col_character()
    ## )

    ## See spec(...) for full column specifications.

    ## Parsed with column specification:
    ## cols(
    ##   .default = col_double(),
    ##   Coach = col_character(),
    ##   Tm = col_character(),
    ##   Remark = col_character()
    ## )

    ## See spec(...) for full column specifications.

    ## Parsed with column specification:
    ## cols(
    ##   .default = col_double(),
    ##   Coach = col_character(),
    ##   Tm = col_character(),
    ##   Remark = col_character()
    ## )

    ## See spec(...) for full column specifications.

    ## Parsed with column specification:
    ## cols(
    ##   .default = col_double(),
    ##   Coach = col_character(),
    ##   Tm = col_character(),
    ##   Remark = col_character()
    ## )

    ## See spec(...) for full column specifications.

    ## Parsed with column specification:
    ## cols(
    ##   .default = col_double(),
    ##   Coach = col_character(),
    ##   Tm = col_character(),
    ##   Remark = col_character()
    ## )

    ## See spec(...) for full column specifications.

    ## Parsed with column specification:
    ## cols(
    ##   .default = col_double(),
    ##   Coach = col_character(),
    ##   Tm = col_character(),
    ##   Remark = col_character()
    ## )

    ## See spec(...) for full column specifications.

    ## Parsed with column specification:
    ## cols(
    ##   .default = col_double(),
    ##   Coach = col_character(),
    ##   Tm = col_character(),
    ##   Remark = col_character()
    ## )

    ## See spec(...) for full column specifications.

    ## Parsed with column specification:
    ## cols(
    ##   .default = col_double(),
    ##   Coach = col_character(),
    ##   Tm = col_character(),
    ##   Remark = col_character()
    ## )

    ## See spec(...) for full column specifications.

    ## Parsed with column specification:
    ## cols(
    ##   .default = col_double(),
    ##   Coach = col_character(),
    ##   Tm = col_character(),
    ##   Remark = col_character()
    ## )

    ## See spec(...) for full column specifications.

    ## Parsed with column specification:
    ## cols(
    ##   .default = col_double(),
    ##   Coach = col_character(),
    ##   Tm = col_character(),
    ##   Remark = col_character()
    ## )

    ## See spec(...) for full column specifications.

    ## Parsed with column specification:
    ## cols(
    ##   .default = col_double(),
    ##   Coach = col_character(),
    ##   Tm = col_character(),
    ##   Remark = col_character()
    ## )

    ## See spec(...) for full column specifications.

    ## Parsed with column specification:
    ## cols(
    ##   .default = col_double(),
    ##   Tm = col_character()
    ## )

    ## See spec(...) for full column specifications.

    ## Parsed with column specification:
    ## cols(
    ##   .default = col_double(),
    ##   Tm = col_character()
    ## )

    ## See spec(...) for full column specifications.

    ## Parsed with column specification:
    ## cols(
    ##   .default = col_double(),
    ##   Tm = col_character()
    ## )

    ## See spec(...) for full column specifications.

    ## Parsed with column specification:
    ## cols(
    ##   .default = col_double(),
    ##   Tm = col_character()
    ## )

    ## See spec(...) for full column specifications.

    ## Parsed with column specification:
    ## cols(
    ##   .default = col_double(),
    ##   Tm = col_character()
    ## )

    ## See spec(...) for full column specifications.

    ## Parsed with column specification:
    ## cols(
    ##   .default = col_double(),
    ##   Tm = col_character()
    ## )

    ## See spec(...) for full column specifications.

    ## Parsed with column specification:
    ## cols(
    ##   .default = col_double(),
    ##   Tm = col_character()
    ## )

    ## See spec(...) for full column specifications.

    ## Parsed with column specification:
    ## cols(
    ##   .default = col_double(),
    ##   Tm = col_character()
    ## )

    ## See spec(...) for full column specifications.

    ## Parsed with column specification:
    ## cols(
    ##   .default = col_double(),
    ##   Tm = col_character()
    ## )

    ## See spec(...) for full column specifications.

    ## Parsed with column specification:
    ## cols(
    ##   .default = col_double(),
    ##   Tm = col_character()
    ## )

    ## See spec(...) for full column specifications.

    ## Parsed with column specification:
    ## cols(
    ##   .default = col_double(),
    ##   Tm = col_character(),
    ##   Player = col_character(),
    ##   Pos = col_character(),
    ##   `College/Univ` = col_character()
    ## )

    ## See spec(...) for full column specifications.

    ## Parsed with column specification:
    ## cols(
    ##   .default = col_double(),
    ##   Tm = col_character(),
    ##   Player = col_character(),
    ##   Pos = col_character(),
    ##   `College/Univ` = col_character()
    ## )

    ## See spec(...) for full column specifications.

    ## Parsed with column specification:
    ## cols(
    ##   .default = col_double(),
    ##   Tm = col_character(),
    ##   Player = col_character(),
    ##   Pos = col_character(),
    ##   `College/Univ` = col_character()
    ## )

    ## See spec(...) for full column specifications.

    ## Parsed with column specification:
    ## cols(
    ##   .default = col_double(),
    ##   Tm = col_character(),
    ##   Player = col_character(),
    ##   Pos = col_character(),
    ##   `College/Univ` = col_character()
    ## )

    ## See spec(...) for full column specifications.

    ## Parsed with column specification:
    ## cols(
    ##   .default = col_double(),
    ##   Tm = col_character(),
    ##   Player = col_character(),
    ##   Pos = col_character(),
    ##   `College/Univ` = col_character()
    ## )

    ## See spec(...) for full column specifications.

    ## Parsed with column specification:
    ## cols(
    ##   .default = col_double(),
    ##   Tm = col_character(),
    ##   Player = col_character(),
    ##   Pos = col_character(),
    ##   `College/Univ` = col_character()
    ## )

    ## See spec(...) for full column specifications.

    ## Parsed with column specification:
    ## cols(
    ##   .default = col_double(),
    ##   Tm = col_character(),
    ##   Player = col_character(),
    ##   Pos = col_character(),
    ##   `College/Univ` = col_character()
    ## )

    ## See spec(...) for full column specifications.

    ## Parsed with column specification:
    ## cols(
    ##   .default = col_double(),
    ##   Tm = col_character(),
    ##   Player = col_character(),
    ##   Pos = col_character(),
    ##   `College/Univ` = col_character()
    ## )

    ## See spec(...) for full column specifications.

    ## Parsed with column specification:
    ## cols(
    ##   .default = col_double(),
    ##   Tm = col_character(),
    ##   Player = col_character(),
    ##   Pos = col_character(),
    ##   `College/Univ` = col_character()
    ## )

    ## See spec(...) for full column specifications.

    ## Parsed with column specification:
    ## cols(
    ##   .default = col_double(),
    ##   Tm = col_character(),
    ##   Player = col_character(),
    ##   Pos = col_character(),
    ##   `College/Univ` = col_character()
    ## )

    ## See spec(...) for full column specifications.

    ## Parsed with column specification:
    ## cols(
    ##   .default = col_double(),
    ##   Tm = col_character()
    ## )

    ## See spec(...) for full column specifications.

    ## Parsed with column specification:
    ## cols(
    ##   .default = col_double(),
    ##   Tm = col_character()
    ## )

    ## See spec(...) for full column specifications.

    ## Parsed with column specification:
    ## cols(
    ##   .default = col_double(),
    ##   Tm = col_character()
    ## )

    ## See spec(...) for full column specifications.

    ## Parsed with column specification:
    ## cols(
    ##   .default = col_double(),
    ##   Tm = col_character()
    ## )

    ## See spec(...) for full column specifications.

    ## Parsed with column specification:
    ## cols(
    ##   .default = col_double(),
    ##   Tm = col_character()
    ## )

    ## See spec(...) for full column specifications.

    ## Parsed with column specification:
    ## cols(
    ##   .default = col_double(),
    ##   Tm = col_character()
    ## )

    ## See spec(...) for full column specifications.

    ## Parsed with column specification:
    ## cols(
    ##   .default = col_double(),
    ##   Tm = col_character()
    ## )

    ## See spec(...) for full column specifications.

    ## Parsed with column specification:
    ## cols(
    ##   .default = col_double(),
    ##   Tm = col_character()
    ## )

    ## See spec(...) for full column specifications.

    ## Parsed with column specification:
    ## cols(
    ##   .default = col_double(),
    ##   Tm = col_character()
    ## )

    ## See spec(...) for full column specifications.

    ## Parsed with column specification:
    ## cols(
    ##   .default = col_double(),
    ##   Tm = col_character()
    ## )

    ## See spec(...) for full column specifications.

    attend <- rbind(attend2010, attend2011, attend2012, attend2013, attend2014,
                    attend2015, attend2016, attend2017, attend2018, attend2019)

    coach <- rbind(coaches2010, coaches2011, coaches2012, coaches2013, coaches2014,
                   coaches2015, coaches2016, coaches2017, coaches2018, coaches2019)

    def <- rbind(def2010, def2011, def2012, def2013, def2014,
                 def2015, def2016, def2017, def2018, def2019)

    draft <- rbind(draft2010, draft2011, draft2012, draft2013, draft2014,
                   draft2015, draft2016, draft2017, draft2018, draft2019)

    off <- rbind(off2010, off2011, off2012, off2013, off2014,
                 off2015, off2016, off2017, off2018, off2019)
