# Amazon Product Recommendation System

## Problem
Build a system that recommends electronics products to Amazon users based on their past ratings.

## Data
Amazon Electronics ratings (user ID, product ID, rating, timestamp), 7.8 million ratings in the raw file. To reduce sparsity, the data was filtered to users with at least 50 ratings and products with at least 5 ratings, leaving 65,290 ratings from 1,540 users on 5,689 products.

Source: `ratings_Electronics.csv` from the [Amazon product data](https://jmcauley.ucsd.edu/data/amazon/) collection by Julian McAuley (UCSD). The file is about 300 MB, so it is not included here. Place it in this folder to run the notebook.

## Approach
1. EDA on the filtered data: rating distribution, sparsity, most active users.
2. Rank-based (popularity) recommendations with a minimum interaction cutoff.
3. User-user and item-item collaborative filtering with KNNBasic, tuned with GridSearchCV.
4. Matrix factorization with SVD, tuned with GridSearchCV.
5. Evaluation with RMSE and precision, recall, and F1 at k = 10 (relevance threshold 3.5).

## Results
| Model | RMSE | Precision@10 | Recall@10 | F1@10 |
|---|---|---|---|---|
| User-user baseline | 1.0012 | 0.855 | 0.858 | 0.856 |
| User-user optimized | 0.9527 | 0.847 | 0.894 | 0.870 |
| Item-item baseline | 0.9950 | 0.838 | 0.845 | 0.841 |
| Item-item optimized | 0.9578 | 0.839 | 0.880 | 0.859 |
| SVD baseline | 0.8882 | 0.853 | 0.880 | 0.866 |
| SVD optimized | 0.8808 | 0.854 | 0.878 | 0.866 |

The optimized SVD model was chosen as the final model. It has the lowest RMSE, an F1 within 0.004 of the best, and it makes a personalized prediction for every user and product pair, while the KNN models often fall back to the global mean when there are too few neighbors.

## Recommendations
Use a hybrid approach: popularity based lists for new users, SVD for users with enough history, and item-item similarity for "customers also liked" sections on product pages. Prompt users to rate purchases to reduce sparsity.
