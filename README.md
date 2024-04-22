![image](https://github.com/Hariveeraprasad-2006/Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn/assets/145049988/b3d3181c-19d9-48eb-9f26-5debbcb40be3)# Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn

## AIM:
To write a program to implement the Decision Tree Classifier Model for Predicting Employee Churn.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import pandas module and import the required data set.
2. Find the null values and count them.
3. Count number of left values.
4. From sklearn import LabelEncoder to convert string values to numerical values.
5. From sklearn.model_selection import train_test_split.
6. Assign the train dataset and test dataset.
7. From sklearn.tree import DecisionTreeClassifier.
8. Use criteria as entropy.
9. From sklearn import metrics.
10. Find the accuracy of our model and predict the require values. 

## Program:
```
/*
Program to implement the Decision Tree Classifier Model for Predicting Employee Churn.
Developed by: Arikatla Hari Veera Prasad
RegisterNumber:  212223240014

*/
```
```
import pandas as pd
data=pd.read_csv("Employee.csv")
data.head()
data.tail()
```

## Output:
![image](https://github.com/Hariveeraprasad-2006/Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn/assets/145049988/9c62a6ea-a990-435d-8030-e1b918cf2051)
```
data.isnull().sum()

```
## Output:
![image](https://github.com/Hariveeraprasad-2006/Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn/assets/145049988/6deb602d-3ed2-4a4f-8901-ade6a4fa5a0e)
```
data["left"].value_counts
```
## Output:
![image](https://github.com/Hariveeraprasad-2006/Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn/assets/145049988/70a487d5-627a-4f5e-b13c-9c6ea3251227)
```
from sklearn.preprocessing import LabelEncoder
le=LabelEncoder()
data["salary"]=le.fit_transform(data["salary"])
data.head()
```
## Output:
![image](https://github.com/Hariveeraprasad-2006/Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn/assets/145049988/646deb98-db80-4d0a-9822-219b90af7e0f)
```
x=data[["satisfaction_level","last_evaluation","number_project","average_montly_hours","time_spend_company","Work_accident","promotion_last_5years","salary"]]
x.head()
```
## Output:
![image](https://github.com/Hariveeraprasad-2006/Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn/assets/145049988/cde110a1-3ccf-4d02-84bb-f16dd2c7418d)
```
y=data["left"]
from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.2,random_state=100)
from sklearn.tree import DecisionTreeClassifier
dt=DecisionTreeClassifier(criterion="entropy")
dt.fit(x_train,y_train)
```
## Output:
![image](https://github.com/Hariveeraprasad-2006/Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn/assets/145049988/154d1b1c-0460-4e28-a148-4804e6196cb8)
```
y_pred=dt.predict(x_test)
from sklearn import metrics
accuracy=metrics.accuracy_score(y_test,y_pred)
accuracy
```
## Output:
![image](https://github.com/Hariveeraprasad-2006/Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn/assets/145049988/f09bb0e1-0790-4671-94f0-f0192cbf0baa)
```
dt.predict([[0.5,0.8,9,260,6,0,1,2]])
```
## Output:
![image](https://github.com/Hariveeraprasad-2006/Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn/assets/145049988/0b0d1612-0257-43bc-9513-b840b6080b6b)
## Result:
Thus the program to implement the  Decision Tree Classifier Model for Predicting Employee Churn is written and verified using python programming.
