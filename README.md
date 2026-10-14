# Sampling for Machine Learning — Train-Test Splits

## Objective

In this lab, I used the Titanic dataset to learn how different train-test split methods affect the sample and how data leakage can affect model evaluation.

## Methodology

- Explored the Titanic dataset and compared survival rates across passenger classes.
- Created a naive 80/20 train-test split and compared the survival rates in the training and test sets.
- Created a stratified train-test split to keep the survival rate similar across both sets.
- Checked how passenger-class shares changed across different splits.
- Identified data leakage caused by fitting a StandardScaler before splitting the data.
- Fixed the leakage by fitting the scaler only on the training data and then transforming the test data.
- Repeated the same idea with missing-value imputation using SimpleImputer.
- Wrote a `split_by_share()` function that splits a dataset using a chosen test share and random seed.
- Tested the function with a 30% test split.

## Key Findings

The stratified split kept the survival rates in the training and test sets closer to the overall survival rate than the naive split. I also found that preprocessing steps such as scaling and imputation should be fit only on the training data to avoid data leakage. My `split_by_share()` function passed the lab check and produced 499 training rows and 215 test rows with a 30% test split. The main takeaway from the lab is that how the data is split and prepared can affect how reliable the final model evaluation is.
