This project is part the Udacity program for Data Science Nanodegree. The project explores multi-year trends in the German Northern Sea.

-----------------------------------------------------------
I. INSTALLATION

In addition to the Anaconda distribution, the project uses: folium (for plotting maps), sklearn (for ML algorithms), and plotnine  (for creating charts).

Used user-agent to run the notebook: conda-4.7.11; requests-2.22.0; CPython-3.7.3; Windows-10.0.16299

-----------------------------------------------------------
II. PROJECT MOTIVATION

Understanding wind trends is of importance to energy companies that have offshore wind parks. Such trends could be used to better plan future energy production.

-----------------------------------------------------------
III. FILE DESCRIPTIONS

Analyses were done in the Jupyter notebook entitled: 190919 Multi-year wind trends Schleswig.ipynb

Input files are from the Integrated Global Radiosonde Archive (IGRA) Version 2 (https://www1.ncdc.noaa.gov/pub/data/igra/). This archive consists of quality-controlled radiosonde observations of temperature, humidity, and wind at stations across all continents. Record length and availability of variables varies among stations and over time. In addition monthly means at mandatory pressure levels is included as a supplementary product. The used files will be stored and accessed from the “Input” folder: 

- Metadata for all stations in the dataset: igra2-station-list.txt (available in the Input folder)

- Input files of monthly wind speed averages (for all the stations) along the "x" and "y" axes (East-West and North-South) taken twice a day (at 00:00 and 12:00) at various pressure levels (i.e. heights): uwnd_00z-mly.txt, uwnd_12z-mly.txt, vwnd_00z-mly.txt, vwnd_12z-mly.txt (the notebook downloads the archives and un-zippes them to Input folder)

-----------------------------------------------------------
IV. RESULTS

This analysis shows:

1. Which meteorological station could be used for such an analysis? Schleswig.

2. Is the wind in the North Sea similar to what it was decades ago? Yes. No structural change could be observed.

3. What is the monthly (i.e. intra-year) seasonality of wind? Winter months are the most windy, being almost twice as windy as the lowest windy months, which occur in late spring and early summer.

4. What multi-year wind trends do we observe? No multi-year sinusoidal pattern could be found.

-----------------------------------------------------------
V. KEY TECHNICALITIES

Missing values were mostly imputed through monthly averages across the dataset. The last months of the data were ignored as it had some missing data and the data quality was more important (the last part of the data was used for validation/testing).

The monthly seasonality was established by fitting a regression model with inputs equal to monthly categorical variables.

Multi-year wind trends were explored through a periodic regression model which models a sinusoidal pattern on time-series data.

-----------------------------------------------------------
VI. LICENSING, AUTHORS, ACKNOWLEDGEMENTS

Author: Dumitru Furtuna

Dataset: Durre, Imke; Xungang, Yin; Vose, Russell S.; Applequist, Scott; Arnfield, Jeff. (2016) Integrated Global Radiosonde Archive (IGRA), Version 2. Monthly means for the full period of record for SCHLESWIG station. NOAA National Centers for Environmental Information. DOI:10.7289/V5X63K0Q Accessed 15.06.2019.

Periodic regression model as implemented in: https://www.cdc.gov/mmwr/preview/mmwrhtml/mm5914a3.htm
