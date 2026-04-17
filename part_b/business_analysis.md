# B1
## (a) ML Problem Defination  
Target Variable - items_sold  
Input features (examples)-  
1. Store attributes- store_size, location_type, footfall, competition_density
2. Promotion- promotion_type
3. Time features- month, is_festival, is_weekend
4. Customer demographic
5. Historical performance  
Type of ML Problem - Supervised Regression
Reason for choosing supervised regression-
1. The output is a continuous numeric category.
2. We are predicting the magnitude and not the category. So we are considering regression.

## (b) Items sold over revenue
Revenue is influenced by price changes and the discount offered. A high discount leads to lower revenue but higher unit sold.  
Items sold measures the customer response to promotion. It removes the pricing distortion and reflects the demand generation in a better way.  
Broader Principle: Choosing a target variable that directly represents the business objective rather than affecting by the external factors.

## (c) Better Modelling Strategy  
A single global model is too simple so the better approach is to select hierarchical modeling.
For this we can use the following methods :-
Separate the models by location_type (urban/semi urban/rural)  
Including store_id as feature  
Use multi-level models  
Using hierarchical model works better as different stores respond differently to promotions. This improves accuracy and personalization and also captures heterogeneity across the stores.

