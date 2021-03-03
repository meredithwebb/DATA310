# Lab 3
##### Meredith Webb | Applied Machine Learning | March 2 2021
## Question 3
( I got this question wrong on the Lab, but then I figured out the correct way to do it afterwards): 

import numpy as np

import pandas as pd

from sklearn.model_selection import train_test_split

from sklearn.linear_model import Ridge, Lasso, ElasticNet, LinearRegression

import operator

from sklearn.metrics import mean_squared_error, r2_score

from sklearn.preprocessing import PolynomialFeatures

df = pd.read_csv('L3Data.csv')

x = df[['days online','views','contributions','answers']].values 

y = df['Grade'].values

x_train, x_test, y_train, y_test = train_test_split(x,y,test_size = .25, random_state = 1234)

model = LinearRegression()

model.fit(x_train,y_train)

y_pred = model.predict(x_test)

rmse = np.sqrt(mean_squared_error(y_test, y_pred))

r2 = r2_score(y_test,y_pred)

print(rmse)

print(r2)

**8.324478857196405
-0.8578219976436847**

## Question 7
import numpy as np

import pandas as pd

from sklearn.model_selection import train_test_split

from sklearn.linear_model import Ridge, Lasso, ElasticNet, LinearRegression

import operator

from sklearn.metrics import mean_squared_error, r2_score

from sklearn.preprocessing import PolynomialFeatures

df = pd.read_csv('L3Data.csv')

x = df[['days online','views','contributions','answers']].values 

y = df['Grade'].values

x_train, x_test, y_train, y_test = train_test_split(x,y,test_size = .25, random_state = 1234)

model = LinearRegression()

model.fit(x_train,y_train)

print(len(x_train))

print(len(y_train)) 

**23**
