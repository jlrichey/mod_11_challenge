# Module 11 Challenge - Forecasting Net Prophet

## Overview

In this challenge, I assume the role of growth analyst for MercadoLibre, the largest e-commerce site in Latin America. A Jupyter notebook was produced to import, prepare, analyze and visualize time series company data for the sake of making marketing decisions and revenue forecasts. Three primary data sources were imported that contain Google hourly search trends, closing stock price movement, and daily revenue for MercadoLibre during the study period. 

## Technical Details

The notebook [notebook](forecasting_net_prophet.ipynb), which was developed in Google Colab, loads the following libraries and dependencies.

```python
import numpy as np
import pandas as pd
import holoviews as hv
from prophet import Prophet
import hvplot.pandas
import datetime as dt
%matplotlib inline
```

The data for this project was imported from csv files utilizing the Pandas `.read_csv` method and returned into DataFrames for analysis.  

The following observations were made, and conclusions were drawn:

#### search traffic trends

* The May 2020 Google search traffic for MercadoLibre is 3008.5 above the overall monthly median.
* The "Average Search Traffic by Week of the Year" graph shows a significant drop in search traffic from week 39 to 42. From week 42 to 51 there is a notable increase in traffic. Week 52 illustrates a severe dropoff in average search traffic.
* Midnight is the peak of popularity.
* Tuesday gets the most search traffic for the week.
* Mid October is the lowest point for search traffic in the year.

#### stock price

* Both the "closing price" and "search trend" charts move in tandem to demonstrate a significant drop in late February/early March of 2020. The closing price bottoms out at its lowest point on March 17 and then runs a sideways pattern until it begins to climb on April 1, achieving new highs in May. The search trends continue achieving lower highs than before the late February/early March event, with the exception of a May 5th anomaly.
* The correlation between the "lagged search trends" and the "stock volatility" is approximately -0.15, so there does not seem to be much of a predictable relationship, only a slight negative correlation. The correlation between the "lagged search trends" and the "hourly stock return" is approximately 0.02, which is also not very high.

#### forecasting and predictions (Prophet)

* The near-term forecast for the popularity of MercadoLibre shows a slight dip and then recovery in early to mid-October of 2020.

* Revenue predictions forecast:
  * Most Likely Revenue Forecast: 1,945.45 million,
  * Worst Case Revenue Forecast: 1,772.18 million,
  * Best Case Revenue Forecast: 2,115.97 million.

## Sources

The following sources were consulted in the completion of this project. 

* [Holoviews Plotting Documentation](https://hvplot.holoviz.org/)
* [pandas.Pydata.org API Reference](https://pandas.pydata.org/docs/reference/index.html)
* UCB FinTech Bootcamp instructor-led coding exercises