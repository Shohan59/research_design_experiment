# Research Methodology

## 1. Research Title

Predicting Body Mass in Palmer Penguins Using Ridge Regression and Random Forest

## 2. Refined Research Question

Can Random Forest improve body mass prediction compared with Ridge Regression for adult Palmer Archipelago penguins?

The objective is to compare a regularized linear regression model with a tree-based ensemble model to determine how accurately penguin body mass can be predicted from physical measurements and categorical characteristics.

## 3. Dataset Description

This study uses the Palmer Penguins dataset, which contains measurements of three penguin species: Adelie, Chinstrap, and Gentoo.

Dataset source: https://github.com/allisonhorst/palmerpenguins

The original dataset contains 344 observations and 8 variables. After removing observations with missing or invalid target values, 342 observations remain.

### Input Features

The following variables are used for prediction:

- `bill_length_mm`: Bill length in millimeters.
- `bill_depth_mm`: Bill depth in millimeters.
- `flipper_length_mm`: Flipper length in millimeters.
- `species`: Penguin species.
- `sex`: Recorded sex of the penguin.
- `bill_ratio`: Engineered feature calculated from bill length divided by bill depth.

### Target Variable

`body_mass_g`: Penguin body mass measured in grams.

This is a supervised regression problem because the target variable is continuous.

## 4. Dataset Limitations

The dataset contains a relatively small number of observations collected from three penguin species in the Palmer Archipelago. The original data includes two missing body mass values and eleven missing sex values.

The dataset may not represent penguins from other geographical regions, seasons, or populations. Therefore, the findings should not automatically be generalized beyond the sampled penguins.

## 5. Data Cleaning Plan

The following preprocessing procedures are implemented:

1. Load the dataset using Pandas.
2. Check missing values and duplicate observations.
3. Remove exact duplicate rows, if any.
4. Remove observations with missing or nonpositive body mass.
5. Treat nonpositive physical measurements as missing values.
6. Impute missing numerical predictors using the median.
7. Replace missing categorical values with an unknown category.
8. Encode categorical variables using one-hot encoding.

Numerical imputation, categorical encoding, and scaling are included within machine learning pipelines so that the transformations are fitted using training data only.

This approach reduces the risk of data leakage from validation or test observations.

## 6. Feature Engineering

A new numerical feature called `bill_ratio` is created:

**Bill Ratio = Bill Length / Bill Depth**

This variable represents the relationship between two bill measurements and may help the models capture information about bill shape.

For Ridge Regression, numerical features are standardized using StandardScaler. Random Forest uses numerical imputation without standardization because tree-based models do not require standardized feature scales.

Categorical features are converted into numerical indicators using one-hot encoding.

## 7. Train-Test Split

The cleaned dataset is divided into:

- Training data: 80%.
- Testing data: 20%.

A random seed of 42 is used for reproducibility. The split is stratified by penguin species to maintain species representation in both subsets.

The resulting holdout test set contains 69 observations, while the training set contains 273 observations.

The holdout test set is kept separate from model comparison during cross-validation.

## 8. Machine Learning Models

### Model 1: Ridge Regression

Ridge Regression is a regularized linear regression method that applies an L2 penalty to regression coefficients.

It is selected because penguin physical measurements may be correlated, and regularization can help stabilize coefficient estimation.

The experiment uses Ridge Regression with an alpha value of 1.0.

### Model 2: Random Forest Regression

Random Forest Regression combines predictions from multiple decision trees.

It is selected because it can capture nonlinear relationships and interactions between penguin characteristics without requiring a predefined linear relationship.

The experiment uses 300 trees, a minimum leaf size of 3, and a random seed of 42.

### Baseline Model

A DummyRegressor using the median strategy is included as a baseline.

This allows the predictive models to be compared against a simple approach that predicts the median body mass from the training data.

## 9. Model Evaluation

Two evaluation metrics are used.

### Mean Absolute Error (MAE)

MAE measures the average absolute difference between actual and predicted body mass.

Lower MAE values indicate better predictive accuracy. The result is expressed in grams, making it easy to interpret.

### Root Mean Squared Error (RMSE)

RMSE measures prediction error while giving greater weight to larger errors.

Lower RMSE values indicate better model performance, particularly when large prediction errors are important.

Both metrics are appropriate because body mass prediction is a regression task.

## 10. Cross-Validation

Five-fold cross-validation is performed on the training dataset.

The folds are stratified by penguin species to preserve species representation. All models are evaluated using the same folds.

Cross-validation MAE is used to identify the preferred predictive model before examining the independent holdout results.

The models are subsequently fitted on the full training dataset and evaluated on the holdout test set using MAE and RMSE.

## 11. Experimental Reproducibility

The experiment is implemented using Python in a Jupyter notebook with Pandas, NumPy, Matplotlib, and Scikit-learn.

A fixed random seed is used, and preprocessing is incorporated within model pipelines.

The notebook contains the code, model evaluation tables, visual comparisons, and written findings so that the experimental process can be inspected.

## 12. Expected Outcome

The experiment aims to determine whether Random Forest provides lower prediction errors than Ridge Regression for penguin body mass.

The comparison will also demonstrate whether a nonlinear ensemble method offers meaningful advantages over regularized linear regression on this dataset.

The conclusions will be based on the observed evaluation metrics rather than assuming that one model must perform better.
