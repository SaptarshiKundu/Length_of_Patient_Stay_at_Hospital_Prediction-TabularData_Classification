# Predicting Patient Length of Stay in Hospital

## Project Goal
This is an overview of the project and an in-depth report can be found in this repository. The goal of this project was to take admission data from several hospitals and, using traditional machine learning algorithms, try to predict how long patients would remain in hospital. This would greatly assist with Healthcare Management and planning.

## Dataset
The dataset is called patient_stay.csv and can be found in this repository. It contains ~300,000 samples with 17 features plus the target. The target contained 11 classes which were a range of days that patients would remain in hospital.

## Approach
1) We began by exploring the featuures included in the dataset. A more in-depth look of these features can be found in the report pdf.
2) Preprocessing
    - Examine the dataset for missing data
    - Encode categorical features to be able to read by the algorithm for training
    - Scale Features. Despite scaling not typically being required for tree-based models we incorporated it to attempt to improve accuracy. Features that resembled gaussian distributions were scaled used a standard scaler (this removes mean and scales to unit variance) while a minmax scaler (which squishes all values between 0 and 1) were used for the remaining features.
    - Dimentionality Reduction. Principal Component Analysis (PCA) was attempted to improve accuracy. No meaningful change in accuracy was noted.
3) Feature Selection. Feature selection can be used to remove data that may not be meaningful and as such several methods and number of features were evaluated for benchmark purposoes. Ultimately, we found all features but ID resulted in the highest accuracy.
4) Model Selection and Benchmarking. A Random Forest Classifier and LightBGM model were used and benchmarked with different variations of scalers and features tried for benchmarking purpooses.
5) RandomizedSearchCV. A randomized search was run with different parameters for both models to find the best parameters which led to the highest accuracy results. A randomized search was usued in place of a grid search to save time and resources when finding parameters.

## Conclusion
Using traditional machine learning algorithms we were able to achieve an accuracy of 42.51% using the LightBGM model.
