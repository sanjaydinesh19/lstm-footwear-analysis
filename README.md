# Esckimo Robotics Work Pipeline
## 1. Machine Learning Approach - Random Forest Model
### Description:
The Random Forest Regressor is used to predict `units_sold` based on contextual and numerical features like "Discounts, Promotions, Weather, Festival Season, etc"
Each row in the dataset represents a snapshot in time, the conditions for that product-week, and the model learns to estimate how many units are likely sold under similar conditions.
So it essentially learns a `mapping function` `f(X) → units_sold` from the data, not a sequence or time progression
### Working:
A Random Forest is an ensemble of many Decision Trees working together.
A single decision tree splits the dataset based on feature thresholds, like:
```
if promo_flag == 1:
    if discount_rate > 0.1:
        predict higher sales
    else:
        predict medium sales
else:
    predict lower sales
```
Each tree tries to split the data to minimize prediction error (variance or mean squared error).
A Random Forest grows hundreds of such trees, but introduces randomness to make them diverse. (Random Sample or Random Subset of features)
Once all trees make predictions, the forest takes the average (for regression).
### Future Scope:
Random Forest has no concept of time, that is, each row is treated independently.
It doesn’t know that `week_end_date` values are sequential or that sales last week affect this week.
It doesn’t model seasonality, trends, or lag effects.
It can’t simulate into the future without providing actual future inputs
