# Teleco Churn
I put together a few of the best answers from Kaggle's teleco data which can be found [here](https://www.kaggle.com/radmirzosimov/telecom-users-dataset). I used the results from 
* [Gokul](https://www.kaggle.com/gokulrajkmv/predict-which-customer-will-leave-eda-modeling)
* [Chris](https://www.kaggle.com/docxian/telecom-customer-churn)
* [Dimtry](https://www.kaggle.com/dmitryuarov/customer-churn-eda-prediction)

However, I looked a few different datasets. In this data, we have some missing values for TotalCharges and 0 for tenure. I looked at datasets where the TotalCharges could be 0 or the median (depending on how one may miss to handle missing values), and for tenure, I mapped 0 to either one or the median. The reason being is someone who signs up for a phone service has a week or so before they can exit without penalty. In this instance, I do not view this a churn since it was as if they never signed up. Therefore, a tenure of 0 does not make much sense to me (to others 0 could be okay for them). I figured the person either made it 1 month, in theory having to pay that bill plus cancellation fee, or 0 was just bad data so I used the median. My 4 datasets:
* TotalCharges missin -> 0 and tenure 0 -> 1
* TotalCharges missin -> 0 and tenure 0 -> median
* TotalCharges missin -> median and tenure 0 -> 1
* TotalCharges missin -> median and tenure 0 -> median

I show this 4 sets in the basic analysis and then just use the median case for both for brevity. 

## Data
We have an imbalance dataset. We have 3 customers who do not churn for every 1 that does churn. I will look at modeling with both oversampling and leaving the data as is.