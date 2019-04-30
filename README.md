
[![Travis build
status](https://travis-ci.org/nfox29/photosearcher.svg?branch=master)](https://travis-ci.org/nfox29/photosearcher)
[![Codecov test
coverage](https://codecov.io/gh/nfox29/photosearcher/branch/master/graph/badge.svg)](https://codecov.io/gh/nfox29/photosearcher?branch=master)
[![Project Status: Active – The project has reached a stable, usable
state and is being actively
developed.](https://www.repostatus.org/badges/latest/active.svg)](https://www.repostatus.org/#active)
<!-- README.md is generated from README.Rmd. Please edit that file -->

# photosearcher

The goal of photosearcher is to provide a repeatable methodology for
accessing the Flickr API. More information can be found on the [package
website](https://nfox29.github.io/photosearcher/). For more information
and examples of the functions check out the [package
vignette](https://nfox29.github.io/photosearcher/articles/photosearcher.html).

## Terms of use

This package should be used within accordance of the [Flickr API terms
of use](https://www.flickr.com/help/terms/api).

## Installation

You can install the released version of photosearcher from github with:

``` r
devtools::install_github("nfox29/photosearcher")
```

## Getting and API key

Before using the package users should sign uo for an API key from the
[Flickr development page](https://www.flickr.com/services/apps/create/).
The first function of the package you use you will be prompted to enter
your API key. The API key will then be saved as a .Rda file and be
called to when using any other function

## Package functions

The package currently focuses on the ability to use the Flickr API to
search for images and their metadata throught the flickr.photos.search
method. The package does however supporst a number of other Flickr API
call methods inlcuding the flickr.tags.getRelated and
flickr.places.tagsForPlace methods. The Flickr website offers full [API
Documentation](https://www.flickr.com/services/api/) for all of its call
methods.

## Searching for photo

Here is a quick example of how to search for images

``` r
  #Search for photos of rock climbing betwee 2010 and 2019 in the UK
  foxes <- photo_search(mindate = "2010-01-01",
             maxdate = "2018-01-01",
             text = "rock climbing",
             bbox = "-12.875977,49.210420,2.636719,59.977005",
             has_geo = TRUE)  
```

When the arguement `has_geo` is `TRUE` all images will contain latitude
and longitude infomation. These can be plotted using other packages at
user preference. Here, the images of UK foxes are plotted using
`ggplot2`.

![Rock
climbing](https://github.com/nfox29/photosearcher/blob/master/images/rock_climbing.png?raw=true)

## Issues and bugs

This package requires an internet connection as well as a connection to
the Flickr API, which may not be constantly available If you discover a
bug not associated with connection to the API that is not already
[reported issue](https://github.com/nfox29/photosearcher/issues), please
[open a new issue](https://github.com/nfox29/photosearcher/issues/new)
providing a reproducible example.
