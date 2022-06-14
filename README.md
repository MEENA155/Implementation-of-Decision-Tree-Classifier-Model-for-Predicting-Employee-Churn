# Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn

## AIM:
To write a program to implement the Decision Tree Classifier Model for Predicting Employee Churn.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Import pandas library to read csv or excel file.
2. Import LabelEncoder using sklearn.preprocessing library.
3. Transform the data's using LabelEncoder.
4. Import decision tree classifier from sklearn.tree library to predict the values.
5. Find the accuracy of the model.
6. Predict the values.
7. End the program.
## Program:
```
/*
Program to implement the Decision Tree Classifier Model for Predicting Employee Churn.
Developed by: MEENA.S
RegisterNumber:  212221240028
*/
```
import pandas as pd
data = pd.read_csv("Employee.csv")

data.head()

data.info()

data.isnull().sum()

data["left"].value_counts()

from sklearn.preprocessing import LabelEncoder
le = LabelEncoder()

data["salary"] = le.fit_transform(data["salary"])
data.head()

x = data[["satisfaction_level","last_evaluation","number_project","average_montly_hours","time_spend_company","Work_accident","promotion_last_5years","salary"]]
x.head()

y = data["left"]

from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test = train_test_split(x,y,test_size = 0.2,random_state = 100)

from sklearn.tree import DecisionTreeClassifier
dt = DecisionTreeClassifier(criterion = "entropy")
dt.fit(x_train,y_train)
y_pred = dt.predict(x_test)

from sklearn import metrics
accuracy = metrics.accuracy_score(y_test,y_pred)
accuracy

dt.predict([[0.5,0.8,9,260,6,0,1,2]])
## Output:
DATA.HEAD():
![image](https://user-images.githubusercontent.com/94677128/173615044-db029c2c-15be-4e9d-82f3-f9625b9a6a0b.png)
DATA.INFO():
![image](https://user-images.githubusercontent.com/94677128/173615081-aeb25338-23f7-4ea8-9dc4-e91b1f95426d.png)
DATA.ISNULL().SUM():
![image](https://user-images.githubusercontent.com/94677128/173615138-5a794906-6d52-40d5-ad65-948a3ea1ec14.png)
DATA.VALUE_COUNTS:
![image](https://user-images.githubusercontent.com/94677128/173615185-979bcd9b-ea66-4f72-986e-d19fe59ed644.png)
DATA.HEAD()USING LABLE ENCODER:
![image](https://user-images.githubusercontent.com/94677128/173615218-eb32e912-c21b-480c-8119-c35f44a0f972.png)
[X.HEAD():
![image](https://user-images.githubusercontent.com/94677128/173615246-6076f6b9-a1d3-4df2-98ad-35adc2b40b73.png)
ACCURACY:
![image](https://user-images.githubusercontent.com/94677128/173615276-d26af1a8-7228-4d4b-b68a-41e9d0735d9a.png)
PREDICTION:
![image](https://user-images.githubusercontent.com/94677128/173616198-c1a7978f-f447-405c-b5ad-422e214e853d.png)


## Result:
Thus the program to implement the  Decision Tree Classifier Model for Predicting Employee Churn is written and verified using python programming.
