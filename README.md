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

# Data cleanup and preparation
Columns that did not contain spectral characterstics were dropped, everything else was kept. 
This is because we did not want the results to be affected by other factors. 
The dropped columns only contained information about scan numbers and processing them and not information about the stars themselves. 

- obj_ID : Object Identifier, the unique value that identifies the object in the image cataloge 
- run_ID : Run Number used to identify a specific scan
- rerun_ID : Rerun Number to specify how the image was processed 
- cam_col : Camera column to identify the scanline within the run
- field_ID : Field number to identify each field
- spec_obj_ID : Unique ID used for optical spectroscopic objects 
- plate : plate ID which identifies each plate in SDSS
- MJD : Modified Julian Date which is used to indicate when SDSS data was taken
- fiber_ID : fiber ID which identifies the fiber pointed the light at the focal plane in each observation

### Transforming objects to numerical values
Columns were checked for data types and the class column was found to be an object, therefore it was transformed to numerical values using Label Endcoder and the data was saved as numerical values in the y_encoded variable. 

The columns that contained spectral characteristics were used as being the X feature for the model.
predictor_cols: 'alpha' , 'delta' , 'u' , 'g' , 'r' , 'i' , 'z' , and 'redshift'

### Splitting data
The features 'X' and target variables 'y_encoded' was split into training and testing sets using 'train_test_split'

### Scaling data
We wanted to compare the effect of data scaling vs not scaling the data on the results from the classification models. Joe Kunesh's data is not scaled while Juhaina Alqabaie's data was scaled using Standard Scaler.

# Classification of data
KNN, Random Forest Classifier, and Decision Tree models were mainly used 

## KNN model
- the model was trained to use odd values from 1 to 19 and then the results were plotted. The scaled data yielded higher training and test scores than the unscaled data

## Decision Tree model
- the model yielded very similar results for both scaled and unscaled data. The slight difference was in the Testing Data score, unscaled data showed a score of 0.96356 and the scaled data had a score of 0.9634.

## Random Forest model
- The model was used to evaluate the data by looping through different numbers of estimators 'n_estimators' and 'max_depth'. There were very few differences between the scaled and unscaled data results, the data was very similar. 

# Other techniques 
- Gradient boosting was used to measure accuracy as well
- Undersampling was done through RandomUnderSampler to balance the number of samples in each class

# Undersampled data
All the classification models (KNN, Decision Tree, and Random Forest Classifier) were used to further evaluate the data after resampling it. 

# Confusion matrix
a confusion matrix was built to illustrate the models' performance

# Data source
https://www.kaggle.com/datasets/fedesoriano/stellar-classification-dataset-sdss17?resource=download
