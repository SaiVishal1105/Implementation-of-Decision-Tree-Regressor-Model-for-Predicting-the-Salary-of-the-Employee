# Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee

## AIM:
To write a program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import the standard libraries.
2. Upload the dataset and check for any null values using .isnull() function.
3. .Import LabelEncoder and encode the dataset.
4. Import DecisionTreeRegressor from sklearn and apply the model on the dataset
5. .Predict the values of arrays.
6. Import metrics from sklearn and calculate the MSE and R2 of the model on the dataset.
7. Predict the values of array.
8. Apply to new unknown values.

## Program:
```
Program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.
Developed by: SAI VISHAL D
RegisterNumber: 212223230180
import pandas as pd
data=pd.read_csv("/content/Salary.csv")
data.head()
```
![image](https://github.com/user-attachments/assets/e0ff9ade-27c6-440c-9705-4bcef6ff0ced)
```
data.info()
```
![image](https://github.com/user-attachments/assets/db02560a-e3a8-468e-8039-11b513079e35)
```
data.isnull().sum()
```
![image](https://github.com/user-attachments/assets/ff9c66ff-271d-4882-a355-6cc6288298e4)
```
from sklearn.preprocessing import LabelEncoder
le=LabelEncoder()
data["Position"]=le.fit_transform(data["Position"])
data.head()
```
![image](https://github.com/user-attachments/assets/990a199a-c348-46cc-9d22-a9c63503b058)
```
x=data[["Position","Level"]]
y=data["Salary"]
from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test=train_test_split(x,y, test_size=0.2, random_state=2)
from sklearn.tree import DecisionTreeRegressor
dt=DecisionTreeRegressor()
dt.fit(x_train, y_train)
y_pred=dt.predict(x_test)
from sklearn import metrics
mse=metrics.mean_squared_error(y_test,y_pred)
mse
```
![image](https://github.com/user-attachments/assets/1929a316-9dee-4bf2-94c3-687bee9d5411)
```
r2=metrics.r2_score(y_test,y_pred)
r2
```
![image](https://github.com/user-attachments/assets/2404dc78-1296-43a5-9fbb-726f6abf0551)
```
dt.predict([[5,6]])
```
![image](https://github.com/user-attachments/assets/20ddc012-e98a-4b4a-a74d-215680ff316a)

## Result:
Thus the program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee is written and verified using python programming.
