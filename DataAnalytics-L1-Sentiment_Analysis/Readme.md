# Twitter Sentiment Analysis using Machine Learning

## Project Overview

This project focuses on analyzing and classifying Twitter posts into four sentiment categories: **Positive, Negative, Neutral, and Irrelevant** using Natural Language Processing (NLP) and Machine Learning techniques.

The project uses Python to clean and preprocess tweet text, convert text into numerical features using TF-IDF, and train two classification models: Multinomial Naive Bayes and Logistic Regression.

The models are evaluated using accuracy, precision, recall, F1-score, classification reports, and confusion matrices. Visualizations, including sentiment distribution charts, model comparison charts, and word clouds, are used to understand the dataset and model performance.

## Objectives

- Analyze the distribution of sentiment categories.
- Identify and handle missing tweet records.
- Clean and preprocess text data using NLP techniques.
- Convert text into numerical features using TF-IDF.
- Train and compare multiple machine learning models.
- Evaluate model performance using classification metrics.
- Visualize sentiment patterns using charts and word clouds.
- Examine misclassified tweets to understand model limitations.

## Dataset Information

**Dataset file:** `twitter_training.csv`

The original dataset contains 74,682 rows and four columns.

| Column | Description |
|---|---|
| `Tweet_ID` | Identifier associated with a tweet |
| `Topic` | Topic or entity associated with the tweet |
| `Sentiment` | Sentiment label of the tweet |
| `Tweet` | Original tweet text |

### Data Cleaning

The following cleaning operations were performed:

- Identified 686 missing tweet records.
- Removed rows with missing values in the `Tweet` column.
- Checked for duplicate rows and removed duplicates if present.
- Applied text preprocessing to create a new `Cleaned_Tweet` column.
- Removed tweets that became empty after preprocessing.

**Final cleaned dataset:** 69,988 rows and 5 columns.

The final dataset contains the original columns and the additional `Cleaned_Tweet` column.

## Technologies Used

- **Programming Language:** Python
- **Environment:** Jupyter Notebook / Anaconda
- **Data Processing:** pandas, NumPy
- **Text Processing:** NLTK, Regular Expressions
- **Feature Extraction:** TF-IDF
- **Machine Learning:** scikit-learn
- **Data Visualization:** Matplotlib, Seaborn
- **Word Cloud Visualization:** WordCloud

## Project Workflow

### 1. Data Loading and Exploration

The dataset was loaded using pandas. The project examined its dimensions, column names, data types, missing values, duplicate records, and sentiment distribution.

### 2. Sentiment Distribution Analysis

The dataset contains four sentiment classes:

- Positive
- Negative
- Neutral
- Irrelevant

A count plot was created to visualize the distribution of these classes.

### 3. Text Preprocessing

The tweet text was cleaned using the following operations:

- Converted text to lowercase.
- Removed URLs.
- Removed user mentions.
- Removed hashtag symbols.
- Removed punctuation and special characters.
- Extracted alphabetic tokens.
- Removed common English stopwords.
- Applied lemmatization to reduce words to their base forms.
- Removed empty cleaned tweets.

These operations help prepare unstructured tweet text for machine learning.

### 4. TF-IDF Feature Extraction

Term Frequency–Inverse Document Frequency (TF-IDF) was used to convert the cleaned tweets into numerical features.

The vectorizer was configured with:

- Maximum features: 20,000
- N-gram range: 1–2

This allows the model to use individual words and two-word combinations as features.

### 5. Train-Test Split

The dataset was divided into training and testing sets using an 80/20 split.

- **Training samples:** 55,990
- **Testing samples:** 13,998
- **Random state:** 42
- **Stratification:** Enabled

The TF-IDF vectorizer was fitted on the training text and then applied to the test text.

### 6. Model Training

Two machine learning algorithms were trained.

**Multinomial Naive Bayes**

A probabilistic classification algorithm used as a baseline for text classification.

**Logistic Regression**

A classification algorithm used to predict the sentiment category based on the TF-IDF features.

### 7. Model Evaluation

The models were evaluated using:

- Accuracy
- Weighted precision
- Weighted recall
- Weighted F1-score
- Classification report
- Confusion matrix

Weighted metrics account for the number of samples in each sentiment class.

## Model Performance Results

The following results were obtained from the test dataset.

| Metric | Multinomial Naive Bayes | Logistic Regression |
|---|---:|---:|
| Accuracy | 71.04% | 76.55% |
| Weighted Precision | 72.88% | 76.61% |
| Weighted Recall | 71.04% | 76.55% |
| Weighted F1-score | 70.14% | 76.34% |

### Result Summary

Logistic Regression achieved higher accuracy, precision, recall, and weighted F1-score than Multinomial Naive Bayes in this experiment.

Based on these results, **Logistic Regression was the better-performing model** among the two models tested.

## Visualizations

The project includes the following visualizations:

1. **Sentiment Distribution Chart** — Displays the number of tweets in each sentiment category.
2. **Naive Bayes Confusion Matrix** — Compares actual and predicted sentiment labels.
3. **Logistic Regression Confusion Matrix** — Visualizes the classification results of Logistic Regression.
4. **Model Performance Comparison** — Compares accuracy, precision, recall, and F1-score.
5. **Positive Sentiment Word Cloud** — Displays frequent words in positive tweets.
6. **Negative Sentiment Word Cloud** — Displays frequent words in negative tweets.
7. **Neutral Sentiment Word Cloud** — Displays frequent words in neutral tweets.
8. **Irrelevant Sentiment Word Cloud** — Displays frequent words in irrelevant tweets.

## Error Analysis

The project examined misclassified tweets by comparing their actual sentiment labels with the predictions made by Logistic Regression.

The model produced **3,283 misclassified tweets** in the test set.

Possible challenges in tweet sentiment classification include:

- Sarcasm and irony
- Informal language and slang
- Spelling variations
- Short or incomplete sentences
- Mixed sentiment expressions
- Context-dependent meanings

The error analysis helps identify areas where text preprocessing and classification techniques could be improved.

## How to Run the Project

### Prerequisites

Install Anaconda or Python with Jupyter Notebook.

Install the required libraries by running the following command in a notebook cell:

```python
%pip install pandas numpy matplotlib seaborn scikit-learn nltk wordcloud
```

### Execution Steps

1. Download or clone the project repository.
2. Place `twitter_training.csv` in the same folder as the Jupyter Notebook.
3. Open Anaconda Navigator and launch Jupyter Notebook.
4. Open the project notebook.
5. Run the import and library installation cells.
6. Download the required NLTK resources:

```python
import nltk

nltk.download("stopwords")
nltk.download("wordnet")
nltk.download("omw-1.4")
```

7. Execute the notebook cells in order, from data loading
