# Implementation-of-Simple-Linear-Regression-Model-for-Predicting-the-Marks-Scored

## AIM:
To write a program to predict the marks scored by a student using the simple linear regression model.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm:

1.Import the standard Libraries.<br>
2.Set variables for assigning dataset values.<br>
3.Import linear regression from sklearn.<br>
4.Assign the points for representing in the graph.<br>
5.Predict the regression for marks by using the representation of the graph.<br>
6.Compare the graphs and hence we obtained the linear regression for the given datas.<br>

## Program:
```
/*
Program to implement the simple linear regression model for predicting the marks scored.
Developed by: DINESHKARTHIK N
RegisterNumber: 212223220021
*/


import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from sklearn.metrics import mean_absolute_error,mean_squared_error
df=pd.read_csv('student_scores.csv')
print(df)
df.head(0)
df.tail(0)
print(df.head())
print(df.tail())
x = df.iloc[:,:-1].values
print(x)
y = df.iloc[:,1].values
print(y)
from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=1/3,random_state=0)
from sklearn.linear_model import LinearRegression
regressor = LinearRegression()
regressor.fit(x_train,y_train)
y_pred = regressor.predict(x_test)
print(y_pred)
print(y_test)
#Graph plot for training data
plt.scatter(x_train,y_train,color='black')
plt.plot(x_train,regressor.predict(x_train),color='blue')
plt.title("Hours vs Scores(Training set)")
plt.xlabel("Hours")
plt.ylabel("Scores")
plt.show()
#Graph plot for test data
plt.scatter(x_test,y_test,color='black')
plt.plot(x_train,regressor.predict(x_train),color='red')
plt.title("Hours vs Scores(Testing set)")
plt.xlabel("Hours")
plt.ylabel("Scores")
plt.show()
mse=mean_absolute_error(y_test,y_pred)
print('MSE = ',mse)
mae=mean_absolute_error(y_test,y_pred)
print('MAE = ',mae)
rmse=np.sqrt(mse)
print("RMSE= ",rmse)

```

## Output:
Dataset:

![alt text](image.png)

Head Values:

![1749043425975](image/README/1749043425975.png)

Tail Values:

![1749043466475](image/README/1749043466475.png)

X and Y values:

![alt text](image-1.png)

Predication values of X and Y:

![1749043510441](image/README/1749043510441.png)

MSE,MAE and RMSE:

![1749043532985](image/README/1749043532985.png)

Training Set:

![1749043546674](image/README/1749043546674.png)

Testing Set:

![1749043555031](image/README/1749043555031.png)

## Result:
Thus the program to implement the simple linear regression model for predicting the marks scored is written and verified using python programming.
