# Data Science and Machine Learning Projects

Three end-to-end projects covering unsupervised learning, supervised classification, and recommender systems. Each notebook goes from data cleaning and exploratory analysis through modeling, evaluation, and business recommendations.

| Project | Problem | Methods | Key result |
|---|---|---|---|
| [Customer Segmentation](customer-segmentation/) | Group retail customers into actionable marketing segments | Feature engineering, StandardScaler, K-Means, elbow and silhouette analysis | 4 customer segments profiled with a targeted strategy for each |
| [Lead Conversion Prediction](lead-conversion-prediction/) | Predict which EdTech leads will become paying customers | Decision Tree, Random Forest, GridSearchCV, feature importance | Tuned Decision Tree reached 0.87 test recall |
| [Amazon Recommendation System](amazon-recommendation-system/) | Recommend electronics products from past user ratings | Popularity ranking, user-user and item-item KNN, SVD matrix factorization | Tuned SVD had the lowest RMSE at 0.881 with F1@10 of 0.866 |

## Tools

Python, pandas, NumPy, matplotlib, seaborn, scikit-learn, SciPy, Yellowbrick, Surprise

## Running the notebooks

```bash
pip install -r requirements.txt
jupyter notebook
```

Each project folder has its own README with the dataset source and a summary of findings. Large datasets are not stored in this repo; download links are in each project's README.

## Author

Aman Chatur, Computer Science, Penn State University
