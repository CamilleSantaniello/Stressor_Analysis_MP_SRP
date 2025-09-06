# Stressor_Analysis_MP_SRP

All scripts, input dataset, intermediary datasets, and fitted models are included in the .zip folder. 

# First input dataset 
The first dataset of the tracks is a subset, containing 3 tracks per species (Magellanic Penguins = MP, Southern Rockhopper Penguins =SRP). It has been cleaned and prepared for interpolation before merging all tracks together. The cleaning of the raw output from the GPS device is not included in this repository. Cleaning steps performed beforehand: 
-	Added year column (breeding season)
-	Added Sex for MP (NA for SRP)
-	Merged all files together, adding a column ID and a column species
-	Kept only columns of interests (datetime, lat, long, year, IDs, species and sex)
-	Created a subset of 3 MP and 3 SRP to use here as a the input. 

# External data used in the codes (not included in the folder):
*Code 01_interpolate_tracks:*
-	Shapefile of the coastline, downloaded at: Capas SIG | Instituto Geográfico Nacional (layer 'area de desarollo de fronteras')
  
*Code 02_Environmental_values_gridding*
-	Chl-a values for 1997-2017, downloaded at: 
https://data.marine.copernicus.eu/product/OCEANCOLOUR_GLO_BGC_L4_MY_009_104/download?dataset=cmems_obs-oc_glo_bgc-plankton_my_l4-multi-4km_P1M_202411
-	SST values for 1981-2017, downloaded at:
https://data.marine.copernicus.eu/product/SST_GLO_SST_L4_REP_OBSERVATIONS_010_011/description
-	Fisheries intensity raster values for December of 2014-2017, downloaded at: Global Fishing Watch 
-	Maritime traffic intensity raster values for December of 2014-2017, downloaded at: GMTDS

# Output of the scripts:
-	Yearly exposure score for anthropogenic and climate-driven stressors per species
-	Cumulative exposure score per species
-	Average relative relative frequency in a cell (per species)
-	Fitted models for each exposure score, with associated yearly and spatial predictions for both species

# Notes: 
-	Variation by sex for MP is not included here. The same calculation framework applies, but instead of separating the dataset by species, it was separated by sex. Statistical tests for sex effects are described in the manuscript, with more details found in the Supplementary. 
-	Code for maps are not included. However, all variables used for mapping (i.e. anthropogenic, climate-driven and cumulative exposure scores, average relative frequency, and coastline source) are documented or calculated throughout the included scripts. 
-	This repository uses a small subset for reproducibility. Some species*year cells are missing, leading to less accurate models, wide CIs and unbalanced CLD groups in models’ predictions. 
