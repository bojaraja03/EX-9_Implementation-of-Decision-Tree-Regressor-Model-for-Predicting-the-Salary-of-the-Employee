# Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee

## AIM:
To write a program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import the standard libraries.
2. Upload the dataset and check for any null values using .isnull() function.Import LabelEncoder and encode the dataset.
3. Import DecisionTreeRegressor from sklearn and apply the model on the dataset.Predict the values of arrays.
4. Import metrics from sklearn and calculate the MSE and R2 of the model on the dataset
5. Predict the values of array.
6. Apply to new unknown values.

## Program:
```
/*
Program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.
Developed by: BOJA RAJA G
RegisterNumber:  212225230036
*/
import pandas as pd

import matplotlib.pyplot as plt

from sklearn.tree import DecisionTreeClassifier, plot_tree

data = pd.read_csv("Salary_EX7.csv")

data.head()

data.info()

data.isnull().sum()

from sklearn.preprocessing import LabelEncoder

le = LabelEncoder()

data["Position"] = le.fit_transform(data["Position"])

data.head()

x=data[["Position","Level"]]

y=data["Salary"]

from sklearn.model_selection import train_test_split

x_train, x_test, y_train, y_test = train_test_split(x,y,test_size=0.2,random_state=2)

from sklearn.tree import DecisionTreeRegressor,plot_tree

dt=DecisionTreeRegressor()

dt.fit(x_train,y_train)

y_pred=dt.predict(x_test)

from sklearn import metrics

mse = metrics.mean_squared_error(y_test,y_pred)

mse

r2=metrics.r2_score(y_test,y_pred)

r2

dt.predict(pd.DataFrame([[5,6]], columns=x.columns))

plt.figure(figsize=(20, 8))

plot_tree(dt, feature_names=list(x.columns), filled=True)

plt.show()
```

## Output:
<img width="305" height="228" alt="image" src="https://github.com/user-attachments/assets/ece84967-ffb6-41a6-beab-92bbf4363036" />
<img width="404" height="217" alt="image" src="https://github.com/user-attachments/assets/852e6b1a-e62c-46ee-984f-55fb31c8abcb" />
<img width="177" height="89" alt="image" src="https://github.com/user-attachments/assets/cca05c4d-6d2c-455f-ab56-d9495615f34d" />
<img width="246" height="225" alt="image" src="https://github.com/user-attachments/assets/9ad786de-b5a7-4f81-a44f-46992b452ef9" />
<img width="1261" height="514" alt="image" src="https://github.com/user-attachments/assets/c4e463ee-a93a-46ab-835e-afdd10ad7d65" />



## Result:
Thus the program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee is written and verified using python programming.
