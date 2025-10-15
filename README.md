# Esckimo Robotics Work Pipeline
## 1. Machine Learning Approach - Random Forest Model
### Description:
The Random Forest Regressor is used to predict `units_sold` based on contextual and numerical features like "Discounts, Promotions, Weather, Festival Season, etc"
Each row in the dataset represents a snapshot in time, the conditions for that product-week, and the model learns to estimate how many units are likely sold under similar conditions.
So it essentially learns a `mapping function` `f(X) → units_sold` from the data, not a sequence or time progression
