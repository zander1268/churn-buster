# Churn Buster: Customer Churn Prediction Tool

**Author**: [Alex FitzGerald](https://www.linkedin.com/in/alex-fitzgerald-0734076a/)

![telecom inc header](Visuals/Telecom_inc_header.png)

## Overview

This project focuses on a fictitious software company, Churn Buster, that is pitching their tool to Telecom Inc., a fictitious wireless service company. Churn Buster has built a predictive model to reduce Telecom Inc.'s customer churn. To build the model, Churn Buster analyzed 3,333 Telecom Inc. customer accounts. Churn Buster analyzed several models before choosing the model that produced the desired result. The winning model was a random forest composed of 100 decision trees. The winning model produced an F1 score of 0.80 which significantly improved upon a baseline model's score of 0.25. The model would help Telecom Inc. predict which customers are likely to churn so they could intervene to save the account with discounts and customer support.

## Business Problem

Telecom Inc., an American telecommunications company, is competing with an up-start company, Lightning Wireless, that has eaten into their majority market share in recent years. To regain their market share, Telecom Inc. must first address the issue of customer churn. Telecom Inc. needs a model to help them predict which of customers are likely to churn so they can intervene and save the accounts. They also want to know what factors contribute to churn so they can improve their service to prevent future churn.

To address these business challenges, Churn Buster will sell Telecom Inc. a model that helps predict customer churn. 
To evaluate the performance of this model, Churn Buster will use F1 score because the Telecom Inc. wants to  capture true positives but is also concerned about minimizing false negatives and false positives. False positives are costly because in cases where our model predicts a customer will churn, Telecom Inc. intends to intervene with customer support and discounts. These interventions cost money, [$53K per year salary](https://www.indeed.com/career/customer-service-representative/salaries) for support representatives and discounts subtract from the profitability of each customer they're offered to.

Given their business goals class imbalance of the data (0.81 majority class), F1 score does a better job evaluating the true performance of our model.

## Data

The data for this project was sourced from a [generic telecom churn dataset](https://www.kaggle.com/datasets/becksddf/churn-in-telecoms-dataset) containing 3,333 customer records. Each observation corresponds to a unique customer and is associated with 20 columns of information about their customer (e.g. voicemail plan, daytime minutes) including whether or not the customer churned (our target). The target is imbalanced with the large majority of observations falling in the churn = False binary classification. The data contains phone numbers from the San Francisco bay area associated with customers evenly spread out across 50 U.S. states. There is no indication of when this data was collected.

## Methods
This project focuses on solving a classification problem with a predictive data science model. The problem at hand is predicting a customer's churn status (true/false). The project uses an iterative approach to building a predictive model that's both accurate and interpretable. In the process, I iterated through several model types, feature engineering methods, and hyperparameters.

## Results
The final model significantly improved Telecom Inc.'s ability to predict which customers are likely to churn. Compared to a baseline model, the final model improved F1 score by 0.55. 
- **F1 Score: 0.80**
- **Precision:** 0.90
- **Recall:** 0.72

![Precision & Recall Curve](Visuals/Final_Model_Precision_Recall.png)

Our model balances recall and precision to meet Telecom Inc.'s business need to identify high risk customers without overpredicting churn.

![Confusion Matrix](Visuals/rf_confusion_matrix.png)

The final model makes correct predictions 95% of the time. The model is very strong at correctly predicting which customers are unlikely to churn and minimizing false positives. The model struggles more with capturing all churned customers although when it does predict churn, it's highly accurate.

![Customer Service Calls](Visuals/Customer_Service_Calls_Day_Minutes.png)

The final model is interpretable which is very useful for Telecom Inc. They can use the model to identify a given customer's churn likelihood and which factors influenced their risk profile. Armed with this information, they can take targeted interventions to save the customer. For example, if the customer has many customer service calls, Telecom Inc. can pair them with their most experienced customer service reps to give them the best experience possible. If the customer has a lot of day-time usage, we can offer them a discount on the service. For customers that aren't at risk of churning, they can withhold costly interventions.


## Conclusions

This predictive algorythm solves many of Telecom Inc.'s business challenges related to customer churn
- **Identifies customers who are likely to churn**
- **Seperates high risk customers from low risk customers so they can focus support resources where it's most needed**
- **Identifies key features connected with churn so customer support can engage high risk customers with personalized account saving interventions like discounts or additional support.**

### Limitations & Next Steps

Additional data and model tuning can further improve the model.

- **Limitations** Our model misses 28% of churning customers. The final model is overly fit to training data because F1 score dropped significantly from training to test evaluation.
- **Next Steps** More examples of churn customers to balance classes will improve overfitting issues. Adding customer payment information will improve accuracy. I can explore black-box models to improve recall.
- **Predicting undesirable outcomes.** This modeling could identify animals that are more likely to have undesirable outcomes (e.g. Euthanasia) for targeted medical support or outreach.
 
## For More Information

See the full analysis in the [Jupyter Notebook](./Code/modeling.ipynb) or review this [presentation](./Churn_Buster_presentation.pdf).

For additional info, contact Alex FitzGerald

## Repository Structure

```
├── Code
│   ├── EDA_notebook.ipynb
│   ├── modeling.ipynb
├── Data
│   ├── churn-in-telecoms-dataset.csv
│   ├── cleaned_data.csv
│   ├── feature_importances.csv
├── Visuals
├── Churn_Buster_presentation.pdf
└── README.md
```
