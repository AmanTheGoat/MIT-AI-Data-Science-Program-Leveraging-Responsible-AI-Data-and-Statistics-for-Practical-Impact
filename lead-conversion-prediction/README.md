# ExtraaLearn Lead Conversion Prediction

## Problem
ExtraaLearn, an EdTech startup, generates many leads and needs to know which ones are most likely to convert to paying customers so the sales team can focus its effort.

## Data
`ExtraaLearn.csv`: 4,612 leads with age, occupation, first interaction channel, profile completion, website activity, last activity, marketing channel flags, and conversion status.

## Approach
1. Data overview and sanity checks (no missing values or duplicates).
2. Univariate and bivariate EDA answering five business questions about occupation, first interaction, last activity, marketing channels, and profile completion.
3. One-hot encoding and a stratified 70/30 train/test split.
4. Default and tuned Decision Tree and Random Forest models. Tuning used GridSearchCV with recall as the metric, since missing a lead that would convert is the costlier error.

## Results (test set)
| Model | Accuracy | Recall | Precision | F1 |
|---|---|---|---|---|
| Decision Tree (default) | 0.809 | 0.668 | 0.683 | 0.676 |
| Decision Tree (tuned) | 0.819 | 0.869 | 0.647 | 0.742 |
| Random Forest (default) | 0.858 | 0.734 | 0.779 | 0.756 |
| Random Forest (tuned) | 0.827 | 0.860 | 0.662 | 0.748 |

## Key findings
- First interaction channel is the strongest driver: Website leads convert at about 46% versus about 11% for Mobile App.
- Time spent on the website matters far more than number of visits.
- Higher profile completion means higher conversion (about 7% Low, 19% Medium, 42% High).
- Professionals convert most, and referrals convert best (about 68%) but are a very small channel.

## Recommendations
Use the model to prioritize outreach, improve the mobile app experience, encourage profile completion and time on site, grow the referral program, and reconsider print media spend.
