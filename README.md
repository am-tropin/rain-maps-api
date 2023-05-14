# Berlin Rain Map with RAINVIEWER

The project gathers the image dataset of rain map masks in Europe around Berlin and converts its to gif. 

Libraries: requests, pandas, geopandas, plotly, geopy, datetime, timezonefinder, pytz, PIL, io, glob, os



## Table of contents
- [Datasets](#datasets)



## Datasets

- The image dataset of [past rain maps](https://github.com/am-tropin/rain-maps-api/tree/main/past_png) and [forecast rain maps](https://github.com/am-tropin/rain-maps-api/tree/main/nowcast_png) were gathered from [RainViewer](https://www.rainviewer.com/api/weather-maps-api.html) using **API requests**. Every rain map looks like this image below:

![Example of rain map](https://github.com/am-tropin/rain-maps-api/blob/main/for_readme/berlin_1684070400.png)

- The data are displayed at timestamps that are multiples of 10 minutes (HH:00, HH:10, ..., HH:50). Past data are available for last 2 hours (13 timestamps), and forecast data are available for following 30 minutes (3 timestamps). To gather a full dataset of past data, I launch the code every 2 hours by building **CI/CD pipelines** in **GitHub Actions**. The code is in [rainviewer_api.ipynb](https://github.com/am-tropin/rain-maps-api/blob/main/rainviewer_api.ipynb) file.

- The data of cities with their coordinates and population are downloaded from [simplemaps.com](https://simplemaps.com/data/world-cities) and are marked on the geographic map using **Plotly**. The background map with cities is in [background_png](https://github.com/am-tropin/rain-maps-api/tree/main/background_png) folder. 

- Gathered past images are merged into a gif file and added the background map. The final gif is in [past_gif](https://github.com/am-tropin/rain-maps-api/tree/main/past_gif) folder. The example of result is also below:

![Gif for May 14, 2023](https://github.com/am-tropin/rain-maps-api/blob/main/for_readme/berlin%202023-05-14%2015%3A20%3A19%20CEST_back.gif)
