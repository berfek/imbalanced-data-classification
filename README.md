# Random Oversampling - Binary Classification for Imbalanced Data 
## Overview
This project aims to develop a binary classification model for predicting train delays using historical train data. The dataset contains 31K historical records spanning over three days, with the "Delayed" feature as the binary target column. A "0" indicates no delay, while "1" represents a delay.

To handle the class imbalance in the target variable, I employed techniques like random over-sampling and computed class weights to ensure the model can effectively distinguish between delayed and non-delayed trains.

## Project Description
The dataset consists of various features related to train operations, including DwellBooked, DwellActual, StationNumber, and additional time-related features. The dataset also includes a nested structure, which required normalization to transform it into a usable format.

## Key Steps:
Data Preprocessing:

Feature Normalization: The "Stop" feature was normalized, and "Headcode" was included from the dataset.
Handling Missing Data: Missing values were eliminated, and date columns were converted to the appropriate format.
Feature Engineering: Created cyclical features (sin_time and cos_time) for time-based columns.
Class Imbalance Handling:

The dataset had an imbalanced target variable, with fewer instances of delays. To address this, random over-sampling was applied to balance the class distribution.
Modeling:

Random Forest Classifier: Given the imbalanced dataset, I selected Random Forest as the model for classification, as it performs well in such scenarios.
Hyperparameter Tuning: Applied CalibratedClassifierCV for probability calibration and adjusted model parameters to improve performance.
Evaluation:

Used classification metrics (precision, recall, F1-score) to evaluate the model. Achieved an overall accuracy of 71% with balanced performance for both classes.

##Technologies Used

Programming Languages: Python
Libraries:
Data Preprocessing: pandas, numpy
Machine Learning: scikit-learn, imbalanced-learn
Modeling: RandomForestClassifier, CalibratedClassifierCV
Evaluation: classification_report, GridSearchCV
Data Normalization: pandas, json

## Data
**Historical Train Data**
The data was provided in a JSON format containing records of train operations, including details like DwellBooked, DwellActual, StationNumber, and Delayed (target column). The dataset had some nested structures, which were normalized for use in the model.

**Coordinates Dataset**
A second dataset provided station coordinates, which were merged with the historical dataset to enhance the features.


## Usage
### Step-by-step workflow:
Data Preprocessing:

Read the historical train dataset and station coordinates.
Perform data normalization, including creating cyclical features.
Oversampling:

Use RandomOverSampler to balance the dataset for imbalanced classes.
Model Training:

Split the data into training and test sets (80-20 ratio).
Train the Random Forest Classifier with the oversampled dataset.
Evaluation:

Evaluate the model performance using precision, recall, and F1-score.
