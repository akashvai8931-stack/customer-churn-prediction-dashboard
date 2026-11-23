# Models

- `logreg_final_model.joblib` : the final Logistic Regression model (class weights)
- `scaler_final.joblib` : the scaler, learned on the training data only

## How to load them

```python
import joblib

model = joblib.load("models/logreg_final_model.joblib")
scaler = joblib.load("models/scaler_final.joblib")
```

Scale new data with the scaler first, then give it to the model.

The risk score from this model is a ranking, not a probability. Only load .joblib files from a source you trust.
