# Customer Churn Prediction and Sales Dashboard

A telecom churn project: data cleaning, model comparison, customer segmentation, revenue impact and a Power BI dashboard (an introduction page and five analysis pages). Made during my data science internship at Zidio Development.

## Key results

| Item | Result |
|---|---|
| Customers | 7,043 |
| Churn rate | 26.54% (1,869 churners) |
| Monthly revenue | $456,117 |
| Revenue lost to churn | $139,131 (30.5%) |
| Main model | Logistic Regression with class weights |
| Test ROC-AUC / recall / precision | 0.84 / 79% / 50% |
| High risk level | 34% of customers, 70% of churners |
| Retention watchlist | 1,003 active High-risk customers |

## What is inside

- `notebooks/` : the full Python notebook (cleaning, features, models, segments, risk levels)
- `models/` : the saved Logistic Regression model and scaler
- `dashboard/` : dashboard screenshots and notes
- `report/` : the final project report (PDF)
- `data/` : notes about the data. The data files are not included, because they contain customer IDs.

## Models compared

Cross-validation ROC-AUC (5 folds, training data only):

| Model | ROC-AUC |
|---|---|
| XGBoost | 0.8481 |
| LightGBM | 0.8477 |
| Logistic Regression (balanced) | 0.8458 |
| ANN (scikit-learn) | 0.8354 |
| ANN (TensorFlow/Keras) | 0.8315 |
| Random Forest | 0.8303 |
| Decision Tree | 0.8194 |

Logistic Regression, XGBoost and LightGBM score almost the same, so the simple, explainable model was chosen.

## Dashboard pages

1. **Introduction** : project title, author and mentor
2. **Churn Overview** : churn by contract, internet service, payment method and tenure
3. **Segments and Risk** : 4 K-Means segments and 3 risk levels
4. **Retention Watchlist** : 1,003 active High-risk customers and $77,068 monthly revenue at risk
5. **Patterns and Revenue** : contract by internet service heatmap, churn by tenure, revenue charts
6. **Segment Actions** : ideas to test for each segment

## Limits (honest)

- The risk score is a ranking, not a probability.
- Accuracy fell to the "always no churn" level (73.4%) when recall went up.
- About 45% of High-risk test customers did not leave.
- The results show association, not cause.
- The data has no dates, so an RNN, sales growth by period, Prophet and purchase frequency were not possible.

## How to run

Install the libraries with `pip install -r requirements.txt`, then open `notebooks/Customer_Churn_Python_Clean.ipynb` in JupyterLab (Python 3.13). The data file is not in this repository, so the notebook needs your own copy of the telecom churn data.

## Author

Akash Vaishnav, Data Science Intern, Zidio Development.
