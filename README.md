# Microsoft-X-DSN-FREE-AI-Classes-in-Every-City-Hackathon-Expresso-Churn-Prediction
The problem statement of this Hackathon is to predicts when an airtime customer is likely to churn or not
## Table of Contents
- [Introduction](#introduction)
- [Feature_Engineering](#feature_engineering)
- [Model](#model)
- [Technologies](#technologies)

## Introduction
Expresso is an African telecommunications company that provides customers with airtime and mobile data bundles. The objective of this challenge is to develop a machine learning model to predict the likelihood of each Expresso customer “churning,” i.e. becoming inactive and not making any transactions for 90 days.
This solution will help Expresso to better serve their customers by understanding which customers are at risk of leaving.The evaluation metric for this challenge is Log Loss.

## Feature_Engineering
The dataset was checked for missing values whcih columns with missing data were filled with 0,while EDA was performed to check important information about the data and it variables. The following Feature Engineering was done to the data using the following : 
- ### label_encorder
from sklearn.preprocessing import LabelEncoder
label_encoder = LabelEncoder()
- ### Fit and transform the data
train_box.loc[:,'REGION_label'] = label_encoder.fit_transform(train_box['REGION'].astype(str))
test_box.loc[:,'REGION_label'] = label_encoder.fit_transform(test_box['REGION'].astype(str))

- ### A function was called using re(Extracting numerical value)
import re

def return_mileage(length):
    
    # Search the text for matches
    mile = re.search("\d+", length)
    
    # If a value is returned, use group(0) to return the found value
    if mile is not None:
        return int(mile.group(0))       
train_box.loc[:,"TENURE_um"] = train_box["TENURE"].apply(return_mileage)
print(train_box[["TENURE", "TENURE_um"]].head())
train_df["old peak"] = train_df["oldpeak"].astype('int64')

- ### lambda 
lambda was called on 'MGR_T' Column for transformation
train_box.loc[:,'MGR_T']=train_box['MRG'].apply(lambda y: 1 if y=="YES" else 0)

## Model
The model for this use case was built using Catboost and evaluated on log_loss as well as Accuracy
The model gave a log loss of  0.256019409719239 and acc_score 0.8770625

The model performance on the public and private leaderboard was 0.251802394 and 0.247434682 respectively , placing me 11th in the competition out of over 150 participants 


## Technologies
- jupyter notebook
- python
- Pandas
- Skick_learn
### link to the hackathon
https://zindi.africa/competitions/microsoft-x-dsn-free-ai-classes-in-every-city-hackathon-expresso-churn-prediction/leaderboard

