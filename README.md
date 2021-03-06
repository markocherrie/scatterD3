`scatterD3` is an HTML R widget for interactive scatter plots visualization.
It is based on the [htmlwidgets](http://www.htmlwidgets.org/) R package and on
the [d3.js](https://d3js.org/) javascript library.

![CRAN Downloads](https://cranlogs.r-pkg.org/badges/last-month/scatterD3)
[![Travis-CI Build Status](https://travis-ci.org/juba/scatterD3.svg?branch=master)](https://travis-ci.org/juba/scatterD3)
[![CRAN_Status_Badge](https://www.r-pkg.org/badges/version/scatterD3)](https://cran.r-project.org/package=scatterD3)

## Features

Here is a small preview of what you will get :

![example](https://raw.github.com/juba/scatterD3/master/resources/scatterD3.gif)

Take a look at
the
[visual guide](https://rawgit.com/juba/scatterD3/master/vignettes/introduction.html) for
a list of features and examples. You can also test it live with
the [sample shiny app](https://data.nozav.org/app/scatterD3/).


## Installation

Install latest stable release from CRAN :

    install.packages("scatterD3")

Or from Github for the latest, bleeding edge, full of bugs version :

    devtools::install_github("juba/scatterD3")

## Usage

Quick example of the `scatterD3`  function based on the `mtcars` dataset :

```{r}
mtcars$names <- rownames(mtcars)
scatterD3(data = mtcars, x = wt, y = mpg, lab = names,
          col_var = cyl, symbol_var = am,
          xlab = "Weight", ylab = "Mpg", col_lab = "Cylinders",
          symbol_lab = "Manual transmission")
```


See [the visual guide](https://rawgit.com/juba/scatterD3/master/vignettes%2Fintroduction.html) for a step-by-step guide and details about the different function arguments.

## Shiny integration

Like every R HTML widget, shiny integration is straightforward. But as a D3
widget, `scatterD3` is *updatable* : changes in settings or data can be
displayed via smooth transitions instead of a complete chart redraw, which can
provide interesting visual clues.

Furthermore, `scatterD3` provides some additional handlers and callback hooks
for a more complete JavaScript interactivity and integration.

The [sample scatterD3 shiny app](http://data.nozav.org/app/scatterD3/) allows
you to see the different features described here. You
can [check its source code on GitHub](https://github.com/juba/scatterD3_shiny_app)
and the [visual guide](https://rawgit.com/juba/scatterD3/master/vignettes%2Fintroduction.html) for
a better understanding of the different arguments.


## Credits

This package has been made possible by :

-   Michael Bostock's incredible [d3.js](https://d3js.org/) library and documentation
-   RStudio's [shiny](http://shiny.rstudio.com/) and [htmlwidgets](http://www.htmlwidgets.org/) packages
-   Susie Lu's [d3-legend](https://github.com/susielu/d3-legend) module
-   Rob Moore's [article on reusable d3.js charts](http://www.toptal.com/d3-js/towards-reusable-d3-js-charts)
-   Speros Kokenes' [d3 lasso plugin](https://github.com/skokenes/D3-Lasso-Plugin)
