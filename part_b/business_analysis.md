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
>> Reason for choosing supervised regression-
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

# B2  
## (a) Data Joining & Aggregation  
The four table (transactions, store attributes, promotion details, and a calendar) will be joined using the appropriate keys available in the dataset.  
1. The transaction table will be the base table as it contains the core sales information.
2. The calender table will be joined using transaction_date to add features such as is_weekend and is_festival.
3. The promotion detail table will be joined using a promotion identifier (example - promotion_type or promotion_id). If no explicit key is available it can be mapped based on transaction_date if promotions are assigned by date.
4. The store attributes table will be joined using store_id if such a column exists. If store level features (example - store_size, location_type) are already present in the transactions table, then a separate join is not required.  

Aggregations Performed:  
Since transactions are typically at a lower level (daily or per transaction), the data will be aggregated to monthly store-level:  
* items_sold → SUM  
> revenue → SUM (if available)  
> footfall → SUM or average  
> promotion_type → dominant or assigned promotion for that month  
> is_festival → MAX (if any day in the month is a festival)  
is_weekend → proportion or count of weekends



