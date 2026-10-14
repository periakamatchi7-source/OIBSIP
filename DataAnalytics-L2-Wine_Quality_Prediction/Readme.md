# Wine Quality Prediction using Machine Learning

## Project Overview

This project uses machine learning to classify wine quality based on its physicochemical properties, such as acidity, residual sugar, chlorides, density, sulphates, and alcohol content.

The original wine quality scores are grouped into three categories: **Low, Medium, and High**. Three classification algorithms—Random Forest, Stochastic Gradient Descent (SGD), and Support Vector Classifier (SVC)—are trained and evaluated to compare their performance.

The project also includes exploratory data analysis (EDA), correlation analysis, feature importance, confusion matrices, and model performance visualizations.

## Objectives

- Analyze the Wine Quality dataset.
- Check missing values and duplicate records.
- Explore the distribution of wine quality scores.
- Visualize chemical feature distributions and correlations.
- Group quality scores into Low, Medium, and High categories.
- Train and compare three machine learning classification models.
- Evaluate models using accuracy, precision, recall, and F1-score.
- Identify important features using Random Forest feature importance.

## Dataset Information

**Dataset:** `WineQT.csv`

The dataset contains 1,143 rows and 13 original columns.

### Features

The physicochemical features used for prediction are:

- Fixed acidity
- Volatile acidity
- Citric acid
- Residual sugar
- Chlorides
- Free sulfur dioxide
- Total sulfur dioxide
- Density
- pH
- Sulphates
- Alcohol

**Target variable:** `quality`

The `Id` column is not included among the model's input features.

## Quality Group Classification

The original numerical quality scores are converted into three categories:

| Quality Score | Category |
|---|---|
| 3–4 | Low |
| 5–6 | Medium |
| 7–8 | High |

### Class Distribution

| Quality Group | Number of Samples |
|---|---:|
| Low | 39 |
| Medium | 945 |
| High | 159 |
| **Total** | **1,143** |

The dataset is imbalanced, with the Medium category representing most observations. This imbalance is important when interpreting model performance.

## Technologies Used

- **Programming Language:** Python
- **Environment:** Jupyter Notebook / Anaconda
- **Data Processing:** pandas, NumPy
- **Data Visualization:** Matplotlib, Seaborn
- **Machine Learning:** scikit-learn
- **Algorithms:** Random Forest, SGD Classifier, Support Vector Classifier

## Project Workflow

### 1. Data Loading and Cleaning

The dataset is loaded using pandas. Its dimensions, column names, data types, missing values, and duplicate records are checked.

No missing values or duplicate rows were found in the supplied dataset.

### 2. Exploratory Data Analysis

EDA is performed to understand the dataset and its features.

Visualizations include:

- Wine quality score distribution
- Chemical feature histograms
- Correlation heatmap
- Quality group distribution

### 3. Feature Engineering

The original quality scores are grouped into Low, Medium, and High categories to create a three-class classification problem.

### 4. Train-Test Split

The dataset is divided into training and testing sets using an 80/20 split.

- Training samples: 914
- Testing samples: 229
- Random state: 42
- Stratification: Enabled

Stratification helps preserve the approximate class proportions in both sets.

### 5. Model Training

Three classification models are trained:

**Random Forest:** An ensemble algorithm that combines decision trees to make predictions.

**SGD Classifier:** A linear classification algorithm trained using stochastic gradient descent. StandardScaler is used before classification.

**Support Vector Classifier (SVC):** A classification algorithm that learns decision boundaries between classes. StandardScaler is used before classification, with an RBF kernel.

### 6. Model Evaluation

The models are evaluated using:

- Accuracy
- Weighted precision
- Weighted recall
- Weighted F1-score
- Classification reports
- Confusion matrices

Random Forest feature importance is also analyzed to identify which features contributed most to its predictions.

## Model Performance Comparison

The following results were obtained from the test dataset.

| Model | Accuracy | Weighted Precision | Weighted Recall | Weighted F1-score |
|---|---:|---:|---:|---:|
| Random Forest | 86.03% | 82.82% | 86.03% | 84.29% |
| SGD Classifier | 82.10% | 78.55% | 82.10% | 80.25% |
| Support Vector Classifier | 84.28% | 79.68% | 84.28% | 80.30% |

### Best-Performing Model

Random Forest achieved the highest accuracy and weighted F1-score among the three models tested.

However, the classification reports show that the models did not correctly identify any Low-quality samples in the test set. The class imbalance therefore remains a significant limitation, and accuracy should not be considered the only measure of model quality.

## Visualizations

The project includes:

1. Wine quality score distribution chart
2. Chemical feature distribution histograms
3. Correlation heatmap
4. Quality group distribution chart
5. Random Forest confusion matrix
6. SGD confusion matrix
7. SVC confusion matrix
8. Random Forest feature importance chart
9. Model performance comparison chart

These visualizations help explain the dataset's characteristics and compare the classification models.

## How to Run the Project

### Prerequisites

Install Anaconda or Python with Jupyter Notebook.

Install the required libraries using:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```

### Execution Steps

1. Download or clone the project repository.
2. Place `WineQT.csv` in the same directory as the Jupyter Notebook.
3. Open Anaconda Navigator and launch Jupyter Notebook.
4. Open the Wine Quality Prediction notebook.
5. Run the notebook cells in order.
6. Review the EDA visualizations and correlation heatmap.
7. Train the three classification models.
8. Compare the evaluation metrics, classification reports, and confusion matrices.
9. Examine the Random Forest feature importance chart.

## Suggested Project Structure

```text
Data-Analytics-Task-2-Wine-Quality-Prediction/
│
├── README.md
├── wine_quality_prediction.ipynb
└── WineQT.csv
```

The notebook filename is a suggested name. Replace it with your actual filename if different.

If the dataset cannot be redistributed, include instructions or a source link for obtaining it rather than committing the dataset to a public repository.

## Real-World Applications

Wine quality classification may support:

- Wine quality screening
- Quality-control processes
- Production monitoring
- Identifying samples that need further inspection
- Supporting laboratory analysis

These are potential applications; the model has not been demonstrated as a replacement for professional wine tasting or laboratory testing.

## Limitations and Future Improvements

The dataset has a substantial class imbalance, particularly in the Low-quality category. All three models struggled to identify the Low class in the test set.

Potential improvements include:

- Applying class weighting or resampling techniques.
- Using stratified cross-validation.
- Tuning model hyperparameters.
- Evaluating macro-averaged precision, recall, and F1-score.
- Investigating additional classification algorithms.
- Collecting more examples of underrepresented quality groups.

## Conclusion

This project demonstrates a machine learning workflow for classifying wine quality using physicochemical properties.

Exploratory data analysis, feature engineering, model training, and evaluation were performed using Python and scikit-learn. Random Forest achieved the best overall results among the three tested models, with 86.03% accuracy and an 84.29% weighted F1-score.

Despite these results, the models struggled to classify Low-quality wines. Further work on class imbalance and minority-class performance would be needed before considering practical deployment.

