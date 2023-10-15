# Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee

## AIM:
To write a program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
### Step-1:
Import the libraries and read the data frame using pandas.
### Step-2:
Calculate the null values present in the dataset and apply label encoder.
### Step-3:
Determine test and training data set and apply decison tree regression in dataset.
### Step-4:
calculate Mean square error,data prediction and r2.

## Program:
```
/*
Program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.
Developed by:\IYYANAR S
RegisterNumber: 212222240036
*/
```
```
import pandas as pd
data=pd.read_csv("Salary.csv")
data.head()
data.info()
data.isnull().sum()
from sklearn.preprocessing import LabelEncoder
le=LabelEncoder()
data["Position"]=le.fit_transform(data["Position"])
data.head()
x=data[["Position","Level"]]
x.head()
y=data[["Salary"]]
from sklearn.model_selection import train_test_split
x_train, x_test, y_train, y_test=train_test_split(x,y,test_size=0.2,random_state=2)
from sklearn.tree import DecisionTreeRegressor
dt=DecisionTreeRegressor()
dt.fit(x_train,y_train)
y_pred=dt.predict(x_test)
from sklearn import metrics
mse=metrics.mean_squared_error(y_test, y_pred)
mse
r2=metrics.r2_score(y_test,y_pred)
r2
dt.predict([[5,6]])
```

## Output:
### data.head():
![11](https://github.com/Iyyanar22009120/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/118680259/099d4302-c4b2-4000-b1c6-7c74b13d7be8)

### data.info():
![12](https://github.com/Iyyanar22009120/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/118680259/12bb682e-d5e2-42b3-8918-d1dd657f37c9)

### isnull() & sum() function:
![13](https://github.com/Iyyanar22009120/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/118680259/b437c811-9d38-4b5b-863e-2c5aff718647)

### data.head() for Position:
![14](https://github.com/Iyyanar22009120/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/118680259/b935c598-4058-47e1-b427-30e05737285d)

### MSE value:
![15](https://github.com/Iyyanar22009120/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/118680259/d509c1a5-aa9d-4ae2-b3af-cc6c68a54a1e)

### R2 value:
![16](https://github.com/Iyyanar22009120/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/118680259/a3e5d1de-7b63-490e-a7a5-f5c58c9b4035)

### Prediction value:
![17](https://github.com/Iyyanar22009120/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/118680259/1c88ec81-570d-4cf1-9bca-b6612ba36b18)

## Result:
Thus the program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee is written and verified using python programming.
