# Capstone Project - Earthquake Depth Prediction: Machine Learning Model Report

## 🎯 Problem Statement
Accurately predicting the depth of an earthquake is critical for assessing its potential impact and guiding emergency response. Depth influences several key factors including surface shaking intensity, potential damage, and the risk of a tsunami. This project explores supervised regression models to predict earthquake depth using geophysical features such as magnitude, latitude, longitude, and time-based variables.

## 🧪 Dataset Overview
* 	Features Used: Magnitude, Latitude, Longitude, Epoch (UTC), and other geophysical indicators.
* 	Target Variable: Earthquake depth (in kilometers).
* 	Preprocessing:
* 	Missing values handled via imputation or row removal.
* 	Feature scaling applied using .
* 	Polynomial expansion () used to capture nonlinear relationships.

## 🧠 Models Evaluated
Three regression models were trained and compared:

|                     Model | Description                                       |
| ------------------------- | ------------------------------------------------- |
|  Linear Regression        |  Baseline model - linear relationships            |
|  Random Forest            |  Ensemble of decision trees nonlinear patterns    |
|  Gradient Boosting        |  Sequential tree-based model optimizing residuals |

**Each model was trained on a standardized and optionally polynomial-expanded feature set.**

## 🔍 Hyperparameter Tuning
1. Grid Search ()
* 	Exhaustively searched combinations of:
* 	: [50, 100, 200]
* 	: [None, 10, 20]
* 	: [2, 5]
* 	Scoring metric: Negative Root Mean Squared Error (RMSE)
2. Randomized Search ()
* 	Sampled 20 random combinations from:
* 	: 50–300
* 	: None + range(5, 25)
* 	: 2–9
3. Best Parameters Identified:

## 📊 Visualizations
1. Actual vs. Predicted Scatter Plot
* 	Shows alignment between predicted and true depth values.
* 	Ideal predictions fall along the diagonal line.
2. Residual Plot
* 	Residuals vs. predicted depth reveal bias or variance issues.
* 	A horizontal band around zero indicates good fit.
3. Error Distribution
* 	Histogram of residuals shows error symmetry and outliers.
4. RMSE vs. n_estimators
* 	Line plot reveals performance trends as tree count increases.
* 	Helps identify diminishing returns.

5. RMSE Heatmap
* 	Visualizes RMSE across combinations of  and .
* 	Highlights optimal regions in the hyperparameter space.

## 📈 Model Performance Summary
|                    Model |   RMSE  | R2 Score             |
| ------------------------ | ------- | -------------------- |
| Linear Regression        |   7.88  | 0.29288984004613927  |
| Random Forest            |   5.75  | 0.6238636198190586   |
| Gradient Boosting        |   6.09  | 0.5776302148345258   |

|                     Model                          |   RMSE  | R2 Score             |
| -------------------------------------------------  | ------- | -------------------- |
| Linear Regression Standard / Polynominal Expansion | 7.88    | 0.29                 |

## ✅ Key Findings
* 	Random Forest and Gradient Boosting outperform linear regression, capturing nonlinear relationships in the data.
* 	Polynomial expansion improves linear model performance but adds dimensionality.
* 	Hyperparameter tuning significantly reduces RMSE and improves generalization.
* 	Visual diagnostics confirm model stability and highlight areas for refinement.
