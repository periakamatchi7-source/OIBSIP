# Housing Data Cleaning Using Python

## Project Overview
This project focuses on inspecting, cleaning, and validating a housing dataset using Python. The goal is to improve data consistency and quality so that the dataset can be used for further analysis and machine learning applications.

## Technologies Used
- Python
- Pandas
- NumPy
- Matplotlib

## Dataset Information
The Housing dataset contains **545 rows and 13 columns**, including:
- Price
- Area
- Bedrooms and bathrooms
- Number of stories
- Main road accessibility
- Guestroom and basement availability
- Hot water heating
- Air conditioning
- Parking spaces
- Preferred area
- Furnishing status

## Project Workflow
1. Load the housing dataset using Pandas.
2. Inspect the dataset structure, column names, and data types.
3. Generate a data quality report.
4. Check for missing values and duplicate records.
5. Standardize categorical values by removing extra spaces and converting text to lowercase.
6. Validate numerical values to identify logically invalid entries.
7. Detect potential outliers using the Interquartile Range (IQR) method.
8. Correct numerical and categorical data types.
9. Compare data quality before and after cleaning.
10. Export the cleaned dataset as `Housing_cleaned.csv`.

## Key Findings
- Dataset size: 545 rows and 13 columns.
- Missing values: 0.
- Duplicate records: 0.
- Invalid numerical ranges: None identified by the checks performed.
- Potential outliers: Identified in several numerical columns using the IQR method.
- Data standardization and validation were performed without removing any rows.

## Outlier Handling
Potential outliers were identified using the IQR method. These records were retained because unusual housing prices, property sizes, or other characteristics may represent genuine properties rather than data-entry errors.

## Output
The cleaned dataset is saved as `Housing_cleaned.csv` and is ready for further exploratory data analysis and machine learning applications.

## Conclusion
This project demonstrates a systematic data-cleaning workflow using Python and Pandas. It includes data quality reporting, categorical standardization, numerical validation, outlier detection, and data type correction to produce a consistent and validated housing dataset.
