# House Price Prediction Using Linear Regression

## Project Overview

This project uses machine learning to predict house prices based on property characteristics such as area, number of bedrooms, bathrooms, floors, year built, location, condition, and garage availability.

The project follows a complete machine learning workflow, including data loading, data quality checks, exploratory data analysis (EDA), feature selection, categorical encoding, model training, and performance evaluation.

A Linear Regression model is implemented using Python and scikit-learn. Its performance is evaluated using Mean Squared Error (MSE), Root Mean Squared Error (RMSE), and the R² score.

## Objectives

- Explore the House Price Prediction dataset.
- Check for missing values and duplicate records.
- Analyze house price distributions and descriptive statistics.
- Examine correlations between numerical features and house prices.
- Encode categorical features using One-Hot Encoding.
- Train a Linear Regression model.
- Evaluate predictions using regression metrics.
- Visualize actual versus predicted prices and residuals.
- Interpret model coefficients and identify limitations.

## Dataset Information

**Dataset file:** `House Price Prediction Dataset.csv`

The dataset contains **2,000 rows and 10 columns**.

| Column | Description |
|---|---|
| `Id` | Unique property identifier |
| `Area` | Area of the house |
| `Bedrooms` | Number of bedrooms |
| `Bathrooms` | Number of bathrooms |
| `Floors` | Number of floors |
| `YearBuilt` | Year the house was built |
| `Location` | Property location |
| `Condition` | Condition of the house |
| `Garage` | Indicates garage availability |
| `Price` | House price — target variable |

The `Id` column is excluded from the model because it serves as an identifier rather than a meaningful property characteristic.

## Data Quality Check

The dataset was checked for missing values and duplicate rows.

- Total records: 2,000
- Total columns: 10
- Missing values: 0
- Duplicate rows: 0

Descriptive statistics were also calculated to understand the distribution of numerical variables.

### House Price Statistics

| Statistic | Value |
|---|---:|
| Minimum price | 50,005 |
| Maximum price | 999,656 |
| Average price | 537,676.86 |
| Median price | 539,254 |

*Note: Currency units are not specified in the supplied dataset.*

## Technologies Used

- **Programming Language:** Python
- **Environment:** Jupyter Notebook / Anaconda
- **Data Processing:** pandas, NumPy
- **Data Visualization:** Matplotlib, Seaborn
- **Machine Learning:** scikit-learn
- **Algorithm:** Linear Regression

## Features Used for Prediction

### Numerical Features

- Area
- Bedrooms
- Bathrooms
- Floors
- YearBuilt

### Categorical Features

- Location
- Condition
- Garage

### Target Variable

- `Price`

Categorical features are converted into numerical representations using One-Hot Encoding with `handle_unknown="ignore"`.

The preprocessing and regression steps are combined in a scikit-learn Pipeline.

## Project Workflow

### 1. Data Loading and Exploration

The dataset is loaded using pandas. Its dimensions, column names, data types, missing values, duplicate records, and descriptive statistics are examined.

### 2. Exploratory Data Analysis

The following visualizations are created:

- House price distribution histogram
- House price boxplot
- Numerical feature correlation heatmap

These visualizations help explore price variation and the relationships between numerical features.

### 3. Correlation Analysis

The numerical correlation analysis found that the selected numerical features had very weak linear correlations with house price.

- Floors had the highest positive correlation with Price: approximately `0.0559`.
- Bathrooms had the lowest correlation with Price: approximately `-0.0157`.

Location, Condition, and Garage are categorical features and are included separately through One-Hot Encoding.

### 4. Feature Encoding

One-Hot Encoding is applied to the categorical variables:

- Location
- Condition
- Garage

The original eight selected input features are transformed into 15 encoded and numerical features.

### 5. Train-Test Split

The dataset is divided into training and testing sets.

- Training records: 1,600
- Testing records: 400
- Test size: 20%
- Random state: 42

### 6. Model Training

A Linear Regression model is trained using the selected numerical and categorical features.

The scikit-learn Pipeline combines categorical preprocessing with the regression model, ensuring the same preprocessing is applied when generating predictions.

### 7. Model Evaluation

The trained model predicts house prices for the test dataset. Its performance is evaluated using:

- Mean Squared Error (MSE)
- Root Mean Squared Error (RMSE)
- R² score

Actual-versus-predicted plots, residual plots, and coefficient analysis are also used to inspect model behavior.

## Model Performance

The Linear Regression model produced the following test-set results:

| Evaluation Metric | Result |
|---|---:|
| Mean Squared Error (MSE) | 78,321,466,146.03 |
| Root Mean Squared Error (RMSE) | 279,859.73 |
| R² Score | -0.0067 |

### Interpretation

The negative R² score indicates that the model performed worse on the test data than a baseline that predicts the mean of the test target values.

The RMSE is approximately 279,860 price units, indicating substantial prediction errors relative to the observed price range.

These results suggest that the current Linear Regression model does not predict house prices effectively using the selected features and this dataset.

## Visualizations

The project includes:

1. House price distribution histogram
2. House price boxplot
3. Correlation heatmap
4. Actual versus predicted house prices scatter plot
5. Residual plot
6. Linear Regression coefficient chart

These visualizations help assess the data, prediction errors, and fitted model coefficients.

## Coefficient Analysis

The Linear Regression coefficients describe how the model's predictions change with each feature while holding the other features constant.

In the fitted model:

- Floors had the largest positive coefficient among the numerical features, approximately `23,727.98`.
- Bathrooms had a negative coefficient of approximately `-9,662.25`.
- The encoded `Condition_Fair` feature had a positive coefficient of approximately `20,279.42`.
- The encoded `Condition_Good` feature had a negative coefficient of approximately `-16,744.93`.

Categorical coefficients should be interpreted relative to the reference categories selected by One-Hot Encoding. These coefficients represent model associations, not proof of causal effects.

Because the model's predictive performance is weak, coefficient interpretations should be treated cautiously.

## How to Run the Project

### Prerequisites

Install Anaconda or Python with Jupyter Notebook.

Install the required libraries:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```

### Execution Steps

1. Download or clone the project repository.
2. Place `House Price Prediction Dataset.csv` in the same directory as the notebook.
3. Open Anaconda Navigator and launch Jupyter Notebook.
4. Open the House Price Prediction notebook.
5. Run the cells in order, from data loading to model evaluation.
6. Review the data quality checks and visualizations.
7. Train the Linear Regression model.
8. Examine the evaluation metrics, residual plot, and coefficient chart.

## Suggested Project Structure

```text
Data-Analytics-Task-2-House-Price-Prediction/
│
├── README.md
├── house_price_prediction.ipynb
└── House Price Prediction Dataset.csv
```

The notebook filename is a suggested name; use your actual filename if it differs.

If the dataset cannot be redistributed publicly, include its source or instructions for obtaining it instead of committing the CSV to the repository.

## Limitations and Future Improvements

The current model achieved a negative R² score, indicating poor predictive performance on the test set.

Possible improvements include:

- Investigating how the dataset's prices were generated and whether they reflect meaningful real-world relationships.
- Testing additional regression algorithms, such as Random Forest Regressor and Gradient Boosting.
- Using cross-validation to obtain a more reliable estimate of model performance.
- Tuning model parameters and comparing results against a mean-prediction baseline.
- Examining outliers and feature distributions.
- Exploring additional useful property features if available.

The weak numerical correlations alone do not explain all model behavior; the data-generating process and the categorical features should also be investigated.

## Conclusion

This project demonstrates a complete machine learning workflow for house price prediction using Python and Linear Regression.

The dataset was explored, categorical variables were encoded, and the model was trained using an 80/20 train-test split. Performance was evaluated with MSE, RMSE, and R², supported by prediction plots, residual analysis, and coefficient interpretation.

The model achieved an R² score of approximately `-0.0067`, showing that it did not predict the test-set house prices effectively. Further data investigation, feature improvements, and comparisons with alternative regression algorithms are needed to improve predictive performance.


