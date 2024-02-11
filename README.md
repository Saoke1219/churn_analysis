# churn_analysis
SYRIATEL CUSTOMER CHURN PREDICTION

PROJECT OVERVIEW:

In Syria, the telecommunications industry faces a significant challenge in retaining customers amidst increasing competition and evolving consumer preferences. SyriaTelcom, one of the leading telecom service providers in the country, seeks to reduce customer churn by identifying patterns and factors contributing to customer attrition. High customer churn not only results in revenue loss but also undermines the company's reputation and market position.

Data 

State : Different states of the customers
Account length: number of days a customer's account has been active
Area code : location of the customer
Phone number : customer's phone number
International plan : whether the customer uses the international plan or not
Voice mail plan : whether the customer has subscribed to vmail plan or not
Number vmail messages : if customer has a vmail plan, how many vmail messages do they get
Total day minutes : total number of call minutes used during the day
Total day calls : total number of calls made during the day
Total day charge : total charge on day calls
Total eve minutes : total number of call minutes used in the evening
Total eve calls : total calls made in the evening
Total eve charge : total charge on evening calls
Total night minutes: Total number of call minutes used at night
Total night calls : Total number of night calls
Total night charge : Total charge on night calls
Total intl minutes : total international minutes used
Total intl calls : total number of international calls made
Total intl charge : total charge on international calls
Customer service calls : number of calls made to customer service
Churn : boolean on whether the customer left or not


BUSINESS PROBLEM:
SyriaTel, a telecommunications company, aims to proactively address customer churn to retain valuable customers, reduce revenue loss, and enhance overall customer satisfaction and loyalty. To achieve this objective, SyriaTel seeks to develop a predictive model capable of identifying customers at risk of churn. By leveraging historical customer data and predictive analytics, SyriaTel aims to anticipate potential churn events and implement targeted retention strategies to mitigate churn and foster long-term customer relationships.

OBJECTIVES:
The objective of this project is to analyze SyriaTelcom's customer data to understand the factors influencing churn and develop predictive models to forecast customer attrition. By leveraging machine learning algorithms and predictive analytics, the project aims to:

Identify key features and patterns associated with customer churn and non-churn.
Build predictive models to forecast the likelihood of churn for individual subscribers.
Provide actionable insights to SyriaTelcom for implementing targeted retention strategies and reducing customer attrition.
Enhance customer satisfaction and loyalty by addressing the underlying issues driving churn.
Improve SyriaTelcom's market position and competitiveness in the telecommunications industry by fostering long-term customer relationships.

You will require the following libraries;

import pandas as pd

import numpy as np

import matplotlib.pyplot as plt

%matplotlib inline

import seaborn as sns

import warnings 

warnings.filterwarnings("ignore")

from sklearn.model_selection import train_test_split, cross_val_score

from sklearn.preprocessing import StandardScaler, MinMaxScaler

from sklearn.impute import SimpleImputer

from sklearn.compose import ColumnTransformer

from sklearn.pipeline import Pipeline

from sklearn.preprocessing import LabelEncoder

from sklearn.preprocessing import OneHotEncoder

from sklearn.metrics import classification_report, confusion_matrix

from sklearn.model_selection import GridSearchCV

from sklearn.tree import DecisionTreeClassifier 

from sklearn.linear_model import LogisticRegression

from sklearn.neighbors import KNeighborsClassifier

from sklearn.ensemble import RandomForestClassifier


from sklearn.metrics import accuracy_score, precision_score, recall_score, f1_score, roc_auc_score, roc_curve

Seaborn style:

sns.set(style="whitegrid")




DATA EXPLORATION

In this analysis, the 'churn' feature serves as the dependent variable.The 'churn' variable signifies whether a customer has terminated their contract with SyriaTel. A value of 'True' means a contract termination, while 'False' indicates that the customer has not terminated their contract and maintains an active account.

![Churn_Distribution](https://github.com/Saoke1219/churn_analysis/assets/144167777/9fe78271-f2d2-4579-a28f-c0a00727a95c)



The above pie chart shows the distribution of churned and non-churned syria tel customers.The distribution is indicated in percentage,with 14.5% "true churn" indicates customers who have ended their subscription. 85.5% "false churn" indicates customers who are still active subscribers.This also shows "non-churn") has a much higher count compared to the other class ("churn"), indicating that the dataset has a class imbalance.

![numerical_distribution_plot](https://github.com/Saoke1219/churn_analysis/assets/144167777/ea29c2c6-b04d-41e3-90e6-e7294875f705)


Above are distribution plots of churned and non-churned customers in the numerical category.We observe that non-churned customers are more than churned customers.we also observe that the distribution is normal while that of total international calls is skewed to the right though still normally distributed.









Group 10 Members

Branton Kieti

Beryl Saoke

Lorrah Ngine

Joseph Mangoka

Priscilla Nzula
