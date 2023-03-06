# Base image https://hub.docker.com/u/rocker/
FROM rocker/r-base:4.2.2

LABEL base.image="rocker/r-base"
LABEL software="R"
LABEL software.version="4.2.2"
LABEL website="https://github.com/rocker-org/rocker/tree/master/r-base/4.2.2"
LABEL license="https://github.com/rocker-org/rocker/blob/master/LICENSE"
LABEL maintainer="Adelaide Roguet"
LABEL maintainer.email="adelaide.roguet@slh.wisc.edu"


## install debian packages
RUN apt-get update -qq && apt-get -y --no-install-recommends install \
libxml2-dev \
libcairo2-dev \
libsqlite3-dev \
libmariadbd-dev \
libpq-dev \
libssh2-1-dev \
unixodbc-dev \
libcurl4-openssl-dev \
libssl-dev \
libgdal-dev \
libudunits2-dev \
libharfbuzz-dev \
libfribidi-dev \
libprotobuf-dev \
libv8-dev \ 
libmagick++-dev \
libjq-dev \
librsvg2-dev

## install R-packages
RUN R -e "install.packages(c(\
'data.table', \
'jsonlite', \
'tidyverse', \
'openxlsx', \ 
'heatmaply', \
'kableExtra', \
'DT', \
'leaflet', \
'highcharter', \
'strex', \
'rgdal', \
'hrbrthemes', \
'zipcodeR', \
'sf', \
'plotly', \
'rmarkdown' \
), dependencies = TRUE, repos = 'http://cran.us.r-project.org')"

RUN R -e "devtools::install_github('outbreak-info/R-outbreak-info')"
RUN R -e "devtools::install_github('rstudio/crosstalk', ref = 'joe/feature/filter-select-default')"


# set working directory to /data
WORKDIR /data



