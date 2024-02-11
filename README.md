# churn_analysis
<<<<<<< HEAD
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


SYRIATEL CUSTOMER CHURN PREDICTION

![What-are-5G-Cell-Towers](https://github.com/Saoke1219/churn_analysis/assets/144167777/aa0d9905-3cbe-4848-9712-666e4b21bef8)


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

>>>>>>> 0a2a7a0ae1c178f7b6c36ad4c83ca0869adb38d8
Churn : boolean on whether the customer left or not


BUSINESS PROBLEM:
<<<<<<< HEAD
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


TARGET
=======

SyriaTel, a telecommunications company, aims to proactively address customer churn to retain valuable customers, reduce revenue loss, and enhance overall customer satisfaction and loyalty. To achieve this objective, SyriaTel seeks to develop a predictive model capable of identifying customers at risk of churn. By leveraging historical customer data and predictive analytics, SyriaTel aims to anticipate potential churn events and implement targeted retention strategies to mitigate churn and foster long-term customer relationships.

OBJECTIVES:

The objective of this project is to analyze SyriaTelcom's customer data to understand the factors influencing churn and develop predictive models to forecast customer attrition. By leveraging machine learning algorithms and predictive analytics, the project aims to:

Identify key features and patterns associated with customer churn and non-churn.

Build predictive models to forecast the likelihood of churn for individual subscribers.

Provide actionable insights to SyriaTelcom for implementing targeted retention strategies and reducing customer attrition.

Enhance customer satisfaction and loyalty by addressing the underlying issues driving churn.

Improve SyriaTelcom's market position and competitiveness in the telecommunications industry by fostering long-term customer relationships.

You will require the following libraries;
```
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
```
DATA EXPLORATION

In this analysis, we will be dropping the 'phone number' column as it is a unique identifier for each customer therefore not relevant for analysis. The 'churn' feature serves as the dependent variable.The 'churn' variable signifies whether a customer has terminated their contract with SyriaTel. A value of 'True' means a contract termination, while 'False' indicates that the customer has not terminated their contract and maintains an active account.

![Churn_Distribution](https://github.com/Saoke1219/churn_analysis/assets/144167777/9fe78271-f2d2-4579-a28f-c0a00727a95c)



The above pie chart shows the distribution of churned and non-churned syria tel customers.The distribution is indicated in percentage,with 14.5% "true churn" indicates customers who have ended their subscription. 85.5% "false churn" indicates customers who are still active subscribers.This also shows "non-churn") has a much higher count compared to the other class ("churn"), indicating that the dataset has a class imbalance.

![numerical_distribution_plot](https://github.com/Saoke1219/churn_analysis/assets/144167777/ea29c2c6-b04d-41e3-90e6-e7294875f705)


Above are distribution plots of churned and non-churned customers in the numerical category.We observe that non-churned customers are more than churned customers.we also observe that the distribution is normal while that of total international calls is skewed to the right though still normally distributed.


![numeric_correlation_heatmap](https://github.com/Saoke1219/churn_analysis/assets/144167777/a7b34a79-6976-4b31-b0d7-2f7b477f4b43)


From the correlation heatmap,some of the features in the dataset demonstrate a perfect positive correlation, such as "Total day charge" and "Total day minutes", "Total eve charge" and "Total eve minutes", "Total night charge" and "Total night minutes", and "Total int charge" and "Total int minutes".They have a correlation coefficient of 1.00, indicating perfect multicollinearity.

explore categorical features
categoric_cols = ['state','area code','international plan','voice mail plan']

### DISTRIBUTION OF CATEGORICAL VARIABLES

![voice_mail_plan_count_on_churn](https://github.com/Saoke1219/churn_analysis/assets/144167777/4141d0b3-1499-409a-a7dc-d8fc8ab594a9)

We can observe from the plot above that there is a significantly low churn rate among customers with a voicemail plan.
This indicates customers have a preference of using this plan.



![international_plan_by_churn_status](https://github.com/Saoke1219/churn_analysis/assets/144167777/3b62b438-fe73-49d8-8bfa-2a30acba0bc7)

We have a small number of customers with an international plan howerver we observe a high churn rate among this group.Possible reasons for the high churn rate could be dissatisfaction with the international plan, international plan charges.

### DATA PREPROCESSING AND PREPARATION

Transform "churn"column from true and false to 0s and 1s.
```
new_df2['churn'] = new_df2['churn'].map({True: 1, False: 0}).astype('int')

new_df2.head()

### ONE-HOT ENCODING CATEGORICAL FEATURES

To be able to run a classification model categorical features are transformed into dummy variable values of 0 and 1.

dummy_df2_state = pd.get_dummies(new_df2["state"],dtype=np.int64,prefix="state_is")
dummy_df2_area_code = pd.get_dummies(new_df2["area code"],dtype=np.int64,prefix="area_code_is")
dummy_df2_international_plan = pd.get_dummies(new_df2["international plan"],dtype=np.int64,prefix="international_plan_is",drop_first = True)
dummy_df2_voice_mail_plan = pd.get_dummies(new_df2["voice mail plan"],dtype=np.int64,prefix="voice_mail_plan_is",drop_first = True)


new_df2 = pd.concat([new_df2,dummy_df2_state,dummy_df2_area_code,dummy_df2_international_plan,dummy_df2_voice_mail_plan],axis=1)
new_df2 = new_df2.loc[:,~new_df2.columns.duplicated()]
new_df2 = new_df2.drop(['state','area code','international plan','voice mail plan'],axis=1)

new_df2.head()
```
### SCALING NUMERICAL FEATURE
```
scaler = MinMaxScaler()
def scaling(columns):

    return scaler.fit_transform(new_df2[columns].values.reshape(-1,1))

for i in new_df2.select_dtypes(include=[np.number]).columns:

    new_df2[i] = scaling(i)
    
new_df2.head()

```
FEATURE SCALING & TRAINING
```
# create the X and Y variables (predict and target values)

y = new_df2['churn']

X = new_df2.drop(['churn'], axis=1) 

#split data into train and test sets

X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.25, random_state=42)

print("X_train shape:", X_train.shape)

print("X_test shape:", X_test.shape)

print("y_train shape:", y_train.shape)

print("y_test shape:", y_test.shape)
```
SMOTE

SMOTE is a data resampling technique used to address class imbalance by generating synthetic samples for the minority class.In this case our minority is churned.

#smote is used to address class imbalance in machine learning
```
from imblearn.over_sampling import SMOTE

oversample = SMOTE(k_neighbors=5)

X_smote, y_smote = oversample.fit_resample(X, y)

print(y_smote.value_counts())

```
### MODELLING

### Logistic Regression Model
```
# Create logistic regression model:
lr = LogisticRegression()

# Train the model:
lr.fit(X_train, y_train)

# Make predictions on the training and testing sets:
y_train_pred = lr.predict(X_train)
y_test_pred = lr.predict(X_test)
```
```
# Feature Importances
feature_importance = abs(lr.coef_[0])
feature_importance = 100.0 * (feature_importance / feature_importance.max())[0:10]
sorted_idx = np.argsort(feature_importance)[0:10]
pos = np.arange(sorted_idx.shape[0]) + .5

```
![Logistic Regression_feature_importance](https://github.com/Saoke1219/churn_analysis/assets/144167777/be1988e9-9a08-4d37-beca-386fc2852882)



```
print(classification_report(y_test, y_test_pred, target_names=['0', '1']))
```

```
print('Accuracy score for testing set: ',round(accuracy_score(y_test,y_test_pred),5))
print('F1 score for testing set: ',round(f1_score(y_test,y_test_pred),5))
print('Recall score for testing set: ',round(recall_score(y_test,y_test_pred),5))
print('Precision score for testing set: ',round(precision_score(y_test,y_test_pred),5))
cm_lr = confusion_matrix(y_test, y_test_pred)

```
![CFM_logistic_regression](https://github.com/Saoke1219/churn_analysis/assets/144167777/7ca79361-9a7e-4e1d-92c1-346c4293bb78)



### Decision Tree Model
```
# Create logistic regression model:
dt = DecisionTreeClassifier()

# Train the model:
dt.fit(X_train, y_train)

# Make predictions on the training and testing sets:
y_train_pred = dt.predict(X_train)
y_test_pred = dt.predict(X_test)

```
```
feature_names = list(X_train.columns)
importances = dt.feature_importances_[0:15]
indices = np.argsort(importances)

```
![Decision Tree_feature importance](https://github.com/Saoke1219/churn_analysis/assets/144167777/170179b8-34c9-4ec0-b959-268371c672fa)



```
print(classification_report(y_test, y_test_pred, target_names=['0', '1']))
```
```
print('Accuracy score for testing set: ',round(accuracy_score(y_test,y_test_pred),5))
print('F1 score for testing set: ',round(f1_score(y_test,y_test_pred),5))
print('Recall score for testing set: ',round(recall_score(y_test,y_test_pred),5))
print('Precision score for testing set: ',round(precision_score(y_test,y_test_pred),5))
cm_dt = confusion_matrix(y_test, y_test_pred)
```
![CMF_Decision_tree](https://github.com/Saoke1219/churn_analysis/assets/144167777/54ad5ea1-4739-465e-9d70-9cb2c063cdd3)


### Random Forest
```
# Create logistic regression model:
rf = RandomForestClassifier() 

# Train the model:
rf.fit(X_train, y_train)

# Make predictions on the training and testing sets:
y_train_pred = rf.predict(X_train)
y_test_pred = rf.predict(X_test)

```

```
Importance =pd.DataFrame({"Importance": rf.feature_importances_*100},index = X_train.columns)
print(classification_report(y_test, y_test_pred, target_names=['0', '1']))
```
![Random_forest_feature_importance](https://github.com/Saoke1219/churn_analysis/assets/144167777/a7894253-4650-4156-8abb-3bb80ec2d36d)


```
print('Accuracy score for testing set: ',round(accuracy_score(y_test,y_test_pred),5))
print('F1 score for testing set: ',round(f1_score(y_test,y_test_pred),5))
print('Recall score for testing set: ',round(recall_score(y_test,y_test_pred),5))
print('Precision score for testing set: ',round(precision_score(y_test,y_test_pred),5))
cm_rf = confusion_matrix(y_test, y_test_pred)

```
![CMF_Random_forest](https://github.com/Saoke1219/churn_analysis/assets/144167777/d47e9613-91ee-4aac-a01a-4116134ec1fd)


### MODEL COMPARISON

```
classifiers = [LogisticRegression(),
               RandomForestClassifier(),
               DecisionTreeClassifier()]


# Define a result table as a DataFrame
result_table = pd.DataFrame(columns=['classifiers', 'fpr','tpr','auc'])

# Train the models and record the results
for cls in classifiers:
    model = cls.fit(X_train, y_train)
    yproba = model.predict_proba(X_test)[::,1]
    
    fpr, tpr, _ = roc_curve(y_test,  yproba)
    auc = roc_auc_score(y_test, yproba)
    
    result_table = result_table.append({'classifiers':cls.__class__.__name__,
                                        'fpr':fpr, 
                                        'tpr':tpr, 
                                        'auc':auc}, ignore_index=True)

# Set name of the classifiers as index labels
result_table.set_index('classifiers', inplace=True)

fig = plt.figure(figsize=(8,6))

for i in result_table.index:
    plt.plot(result_table.loc[i]['fpr'], 
             result_table.loc[i]['tpr'], 
             label="{}, AUC={:.3f}".format(i, result_table.loc[i]['auc']))
    
plt.plot([0,1], [0,1], color='black', linestyle='--')

plt.xticks(np.arange(0.0, 1.1, step=0.1))
plt.xlabel("False Positive Rate", fontsize=15)

plt.yticks(np.arange(0.0, 1.1, step=0.1))
plt.ylabel("True Positive Rate", fontsize=15)

plt.title('ROC Curve Analysis', fontweight='bold', fontsize=15)
plt.legend(prop={'size':13}, loc='lower right')

plt.show()

```

![Model_comparison](https://github.com/Saoke1219/churn_analysis/assets/144167777/bf615ed8-ba85-4dbe-adae-994aa96481ba)


he ROC curve is a plot of the true positive rate against the false positive rate of our classifier. The best performing models will have a curve that hugs the upper left of the graph, which is the the random forest classifier in this case.

### MODEL COMPARISON (F1 SCORE)
```
models = [lr,rf,dt]

result = []
results = pd.DataFrame(columns= ["Models","F1"])

for model in models:
    names = model.__class__.__name__
    y_pred = model.predict(X_test)
    f1 = cross_val_score(model,X_test,y_test,cv=10,scoring="f1_weighted").mean()  
    result = pd.DataFrame([[names, f1*100]], columns= ["Models","F1"])
    results = results.append(result)
    
sns.barplot(x= 'F1', y = 'Models', data=results, palette="coolwarm")
plt.xlabel('F1 %')
plt.title('F1 of the models');

```
![Models_comparison_f1_score](https://github.com/Saoke1219/churn_analysis/assets/144167777/51845f88-1cb2-47f1-8504-fc5f9d52e400)

```
The decision treeclassifier has a higher F1_Score.

```
### MODEL COMPARISON (ACCURACY)
```
models = [lr,rf,dt]
result = []
results = pd.DataFrame(columns= ["Models","Accuracy"])

for model in models:
    names = model.__class__.__name__
    y_pred = model.predict(X_test)
    accuracy = accuracy_score(y_test, y_pred)    
    result = pd.DataFrame([[names, accuracy*100]], columns= ["Models","Accuracy"])
    results = results.append(result)
    
    
sns.barplot(x= 'Accuracy', y = 'Models', data=results, palette="coolwarm")
plt.xlabel('Accuracy %')
plt.title('Accuracy of the models');
```
![Model_comparison_Accuracy](https://github.com/Saoke1219/churn_analysis/assets/144167777/bc635835-9083-4b9c-8b8e-42288a49c641)


We are searching for a model that can predict with high accuracy and precision random forest classifier fits those requirements.

```

```




### Collaborators
Lorrah Ngine <lorrah.ngine@student.moringaschool.com> - Lead
Branton Kieti <branton.kieti@student.moringaschool.com>
Joseph Mangoka <joseph.mangoka@student.moringaschool.com>
Beryl Saoke <beryl.saoke@student.moringaschool.com>
Priscilla Nzula <Priscilla.nzula@student.moringaschool.com>
>>>>>>> 0a2a7a0ae1c178f7b6c36ad4c83ca0869adb38d8






<<<<<<< HEAD
Group 10 Members
Branton Kieti
Beryl Saoke
Lorrah Ngine
Joseph Mangoka
Priscilla Nzula
=======
>>>>>>> 0a2a7a0ae1c178f7b6c36ad4c83ca0869adb38d8
