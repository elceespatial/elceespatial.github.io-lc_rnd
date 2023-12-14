# CLIM680 [Final Project](https://github.com/elceespatial/elceespatial.github.io-lc_rnd/blob/main/clim680_FA23_CMIP6_CanESM5_Correlation_Analysis.ipynb)



-- [Previous Course Assignments](https://github.com/elceespatial/elceespatial.github.io-lc_rnd/tree/main/notebooks)

#### Analzying CMIP6 CanESM5 and Diopole Mode Index Analysis of Precipation Analomies and Positive/Negative IOD in the East Africa


## Introuction
***The key science topic you are interested in exploring with your dataset. Describe your scientific topic and why you chose this dataset.***

**Background:** East Africa’s GDP is primarily focused on agriculture and with climate change can cause longer period of extreme rainfall, negatively impact agricultural exports and causing challenges to food security to the communities the rely heavily on farming. During times of positive IOD, heavier rainfall is experienced throughout areas of East Africa washing crops. Comparatively, during times of negative IOD agriculture can dry out and even start brush fires. I am interested in how precipitation is impacted by IOD in areas of East Africa to better understand the correlation and if precipitation is a suitable variable to study climate phoneme in the region.

Research Question:

Q1: What areas in East Africa experience peak cumulative precipitation during period of positive and negative IOD?


## Data Sources: 

**Data: A description of your primary dataset and any additional datasets used e.g. climate indices, comparison datasets.  Should include links or paths to where the datasets are located and some information about the data original source. Should also include any unique information about your data relevant to this class e.g. data is on an irregular grid**


- **[CMIP6]('https://storage.googleapis.com/cmip6/cmip6-zarr-consolidated-stores.csv') The Canadian Earth System Model version 5 Model Description** : The Canadian Earth System Model version 5 (CanESM5) is a global model developed to simulate historical climate change and variability, to make centennial-scale projections of future climate, and to produce initialized seasonal and decadal predictions. CanESM5 is comprised of three-dimensional atmosphere (T63 spectral resolution equivalent roughly to 2.8∘) and ocean (nominally 1∘) general circulation models, a sea-ice model, a land surface scheme, and explicit land and ocean carbon cycle models. The model features relatively coarse resolution and high throughput, which facilitates the production of large ensembles. CanESM5 has a notably higher equilibrium climate sensitivity (5.6 K) than its predecessor, CanESM2 (3.7 K), which we briefly discuss, along with simulated changes over the historical period. CanESM5 simulations contribute to the Coupled Model Intercomparison Project phase 6 (CMIP6) and will be employed for climate science and service applications in Canada. [GMD - The Canadian Earth System Model version 5 (CanESM5.0.3)](https://gmd.copernicus.org/articles/12/4823/2019/)

![CanESM5](https://github.com/elceespatial/elceespatial.github.io-lc_rnd/blob/main/assets/img/CanESM5_SummaryStats.png)


- **Climate Variable**:
Precipitation (kg m-2 s-) The sum of liquid and frozen water, comprising rain and snow, that falls to the Earth's surface. It is the sum of large-scale precipitation and convective precipitation. This parameter does not include fog, dew or the precipitation that evaporates in the atmosphere before it lands at the surface of the Earth. This variable represents amount of water per unit area and time.

- **Dipole Mode Index (DMI)**
![DMI](https://github.com/elceespatial/elceespatial.github.io-lc_rnd/blob/main/assets/img/dipole_viz.png)
Description: Intensity of the IOD is represented by anomalous SST gradient between the western equatorial Indian Ocean (50E-70E and 10S-10N) and the southeastern equatorial Indian Ocean (90E-110E and 10S-0N). This gradient is named as Dipole Mode Index (DMI). When the DMI is positive then, the phenomenon is refereed as the positive IOD and when it is negative, it is refereed as negative IOD. [DMI](https://psl.noaa.gov/gcos_wgsp/Timeseries/DMI/)

Time Interval: Monthly
Time Coverage: 1870 to present
Update Status: Periodically updated



## Code, Methodolgy, and Results -  [Check out Code and Results Here](https://github.com/elceespatial/elceespatial.github.io-lc_rnd/notebooks/clim680_FA23_FinalProject_EA_CanESM5_pr_DMI_Analysis.ipynb)
- Obtain CMIP6 data via Google Cloud
- Plot precipitation for historical CMIP6 data
- Calculate DMI Index 
- Calculate Climatology and Anomalies Create a timeseries of global-average precipitation
- Compare different time periods over precip mm
- Calculate Composite Indices
- Compare anomalies and DIO Index
- Statistical Significance – Pearson’s R


## Summary
***Provide short summary of what you learned from your analysis of your data (both scientific and technical), what you would do next to advance this analysis, and any challenges or issues you encountered/overcame.***


Analysis concluded CanESM5 data may not be most suitable when working with precipitation variables as single climatology with significantly high variability on season time scales and misaligned with ENSO. CanESM5 documentation provides an outline of summary statistics the reproducibility of large-scale climate features. Most importantly for the variable used during this study, pr, reported a .67 rmse for CanESM5 with the rmse for CanESM5-CanESM reported as 0. Additionally, there is weak monthly variability when comparing monthly anomalies compared to observational data when analyzing characteristics of ENSO due to negative patterns of North Atlantic Oscillation. Conversely, CanESM5 does well in tropical areas such as the Indian Ocean which served the study well since the Dipole Model Index is in the Indian Ocean noted when completing p-value testing. 

![p-value](https://github.com/elceespatial/elceespatial.github.io-lc_rnd/blob/main/assets/eastA_precip_anom_corr_pval_map.png)
<img src="./images/eastA_precip_anom_corr_pval_map.png" alt="lasagna">

With CMIP6 comprised of over 30 models, which are also comprised of component models, it was challenging to identify the most performative model for this initial research. A primary challenge I faced was incorporating multiple models and variables into the initial research in a scalable way that would inform provide a comprehensive evaluation of how positive and negative IOD impact countries throughout East Africa. While I was not able to overcome that challenge during this initial research, I have identified open-source packages and learning material to advance this research. Ultimately, I want to incorporate additional climate variables and merge with population and socio-economic variable to support research in climate driven migration in and out of the region of East Africa.

Future of Work Ideas:
- Leveraging Downscaled CMIP6 Data Usage
-- Nearest Grid finder affects to correlation as coordinates can be extremely far from the intended grid cell this can be alleviated using downscaled CMIP6 data.
- Regional Climate Model Seasonal Analysis
-- Regional Climate models appear to have better resolution and more fidelity due to incorporating observational data into RCMs
-- Seasonality in East Africa is different than season used to create global climate models
![diff-seasonality](https://github.com/elceespatial/elceespatial.github.io-lc_rnd/blob/main/assets/img/eastA_precip_anom_2009_MAMJ.png)
- Future analysis of Initial Comparison of SSPs and Observational data
-- High-Resolution Satellite Imagery data (NDVI) compared to GCM precipitation and temperature



