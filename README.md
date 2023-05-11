# Berlin Rain Map with RAINVIEWER

The project gathers the image dataset of rain map masks in Europe around Berlin and converts its to gif. 

Libraries: requests, geopy, datetime, timezonefinder, pytz, PIL, io, glob, os



## Table of contents
- [Datasets](#datasets)



## Datasets

- The image dataset of [past rain maps](https://github.com/am-tropin/rain-maps-api/tree/main/past_png) and [forecast rain maps](https://github.com/am-tropin/rain-maps-api/tree/main/nowcast_png) were gathered from [RainViewer](https://www.rainviewer.com/api/weather-maps-api.html) using **API requests**.

![Example of rain map](https://github.com/am-tropin/rain-maps-api/blob/main/drafts/berlin%1683610200%20(for%20readme).png)

- The data are displayed at timestamps that are multiples of 10 minutes (HH:00, HH:10, ..., HH:50). Past data are available for last 2 hours (13 timestamps), and forecast data are available for following 30 minutes (3 timestamps). To gather a full dataset of past data, I launch the code every 2 hours by building **CI/CD pipelines** in **GitHub Actions**. The code is in [rainviewer_api.ipynb](https://github.com/am-tropin/rain-maps-api/blob/main/rainviewer_api.ipynb) file.

- Gathered past images are merged into a [gif file](https://github.com/am-tropin/rain-maps-api/tree/main/past_gif).

![Gif for May 9-11, 2023](https://github.com/am-tropin/rain-maps-api/blob/main/drafts/berlin%20%202023-05-11%2018%3A25%3A31%20CEST%20(for%20readme).gif)