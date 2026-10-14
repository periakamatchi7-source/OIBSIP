# Customer Segmentation Analysis

## Project Overview
This project focuses on analyzing customer purchasing behavior using the Online Retail dataset. RFM (Recency, Frequency, Monetary) analysis and the K-Means clustering algorithm are used to group customers into meaningful segments based on their purchasing activity and spending patterns.

## Technologies Used
- Python
- Pandas and NumPy
- Matplotlib and Seaborn
- Scikit-learn
- Jupyter Notebook

## Project Workflow
1. Load and explore the Online Retail dataset.
2. Handle missing customer IDs and remove cancelled transactions.
3. Convert invoice dates into datetime format and calculate total transaction amounts.
4. Calculate RFM metrics for each customer.
5. Standardize RFM features using StandardScaler.
6. Apply the Elbow Method to select the number of clusters.
7. Implement K-Means clustering to identify four customer segments.
8. Visualize customer distribution and purchasing behavior.
9. Analyze customer profiles and recommend targeted marketing strategies.

## Customer Segments
- **Cluster 0 – Recent, High-Value Customers:** Customers with recent purchases, high frequency, and high spending.
- **Cluster 1 – Inactive, Low-Engagement Customers:** Customers who have not purchased recently and have relatively low spending.
- **Cluster 2 – Very Frequent, High-Value Customers:** Customers with very frequent purchases and the highest average spending.
- **Cluster 3 – Occasional, Lower-Value Customers:** Customers with moderate recency and comparatively lower purchase frequency and spending.

## Key Results
- Analyzed 397,924 transactions after data cleaning.
- Segmented 4,339 customers into four groups.
- Calculated an average transaction value of 22.39 in the dataset's currency.
- Identified customer groups suitable for loyalty programs, reactivation campaigns, and repeat-purchase promotions.

## Business Recommendations
- Reward high-value customers with loyalty benefits and personalized offers.
- Reactivate inactive customers through targeted discounts and reminders.
- Encourage repeat purchases with product recommendations and bundle offers.
- Review customer segments periodically to monitor changes in purchasing behavior.

## Conclusion
This project demonstrates how RFM analysis and K-Means clustering can help businesses understand customer behavior, personalize marketing campaigns, improve customer retention, and make data-driven business decisions.

## Dataset
Online Retail dataset containing invoice details, product information, quantities, prices, invoice dates, customer IDs, and countries.

