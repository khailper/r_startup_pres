Customizing R Startup
========================================================
author: Karl Hailperin
date: July 20, 2017
autosize: true
## https://github.com/khailper/r_startup_pres

Startup Files 
========================================================

- .Rprofile/.Renviron

- R looks for them in three places on startup (in this order)
    - Current working directory (find with getwd())
    - Your home directory (Sys.getenv("HOME"))
    - R_HOME (i.e. where R is installed)(R.home())
    
.Rprofile
========================================================

- Code that runs on startup.
- Example:


```r
utils::update.packages(ask = FALSE)
library(tidyverse)
```
- Keep it simple; functions you will use almost every session
- Couple other useful functions for .Rprofile
    - ggplot2::theme_set()
    - options()
        - allows you to set things like how many digits to display, how to handle errors, or set stringsAsFactors to default to FALSE

.Renviron
========================================================

- Allows you to store system variables
- Useful for API keys
- Example:


```r
google_api_key <- "24389ryewfhasdkv874qowfruils4q38ruh"
```
Retreived with Sys.getenv("google_api_key")

Words of Warning
========================================================
- .Rprofile can create complications when sharing code
- When sharing code using variables stored in . Renviron, make sure to have common naming conventions

Questions?
========================================================

