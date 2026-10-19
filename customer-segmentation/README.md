# Customer Segmentation with K-Means

## Problem
A retail company wants to move away from generic marketing by identifying distinct customer groups based on demographics, spending, and purchase behavior.

## Data
2,240 customers with 29 features covering demographics, spending by product category over two years, purchase channels, and responses to 6 marketing campaigns.

Source: [Customer Personality Analysis (Kaggle)](https://www.kaggle.com/datasets/imakash3011/customer-personality-analysis). Save the file as `Customer_Personality_Segmentation.csv` in this folder to run the notebook (tab separated).

## Approach
1. Cleaned the data: median imputation for 24 missing incomes, removed unrealistic ages and an income outlier, dropped constant columns.
2. Engineered features: Age, Total_Spending, Total_Purchases, Family_Size, Children, Customer_Days, Total_Accepted_Campaigns.
3. Univariate and multivariate EDA with histograms, boxplots, a correlation heatmap, and scatter plots.
4. Scaled the features and chose k using the elbow plot and silhouette scores.
5. Fit K-Means with k = 4 and profiled the clusters with boxplots, bar plots, and mean summary tables.

## Segments found
| Cluster | Size | Profile |
|---|---|---|
| 0 | 1,060 | Lowest income and spending, largest families, most website visits. Budget constrained, low conversion. |
| 1 | 154 | High income, highest spending and campaign acceptance. Premium, marketing responsive. |
| 2 | 613 | Middle income and spending, most deal purchases. Price sensitive. |
| 3 | 409 | High income and spending but low campaign response. |

## Recommendations
Focus loyalty programs and campaigns on Cluster 1, try catalog and personalized offers for Cluster 3 instead of repeating past campaign formats, use coupons and flash sales for Cluster 2, and test value bundles for Cluster 0 while investigating why its frequent site visits rarely convert.
