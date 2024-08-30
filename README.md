# group-project-2
# Introduction
OSU Bootcamp: Group Project 2

# Project overview
Analyzing stars, galaxies, and quasars based on their characteristics

alpha : Right Ascension angle 
delta : Declination angle 
u : Ultraviolet filter in the photometric system
g : Green filter in the photometric system
r : Red filter in the photometric system
i : Near infrared filter in the photometric system 
z : Infrared filter in the photometric system
redshift : values based in the increase in wavelength

# Data cleanup
Columns that did not contain spectral characterstics were dropped, everything else was kept. 

- obj_ID : Object Identifier, the unique value that identifies the object in the image cataloge 
- run_ID : Run Number used ti identify a specific scan
- rerun_ID : Rerun Number to specify how the image was processed 
- cam_col : Camera column to identify the scanline within the run
- field_ID : Field number to identify each field
- spec_obj_ID : Unique ID used for optical spectroscopic objects 
- plate : plate ID which identifies each plate in SDSS
- MJD : Modified Julian Date which is used to indicate when SDSS data was taken
- fiber_ID : fiber ID which identifies the fiber pointed the light at the focal plane in each observation

# Classification of data
KNN, Randome Forest Classifier, and Dcesion Tree models were used 

# Data source
https://www.kaggle.com/datasets/fedesoriano/stellar-classification-dataset-sdss17?resource=download
