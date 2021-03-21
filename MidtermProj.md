# Midterm Project 
## Meredith Webb | Applied Machine Learning | March 21 2021 
#### * included is my code for the questions I was unsure of *
#### Question 5: 
from sklearn.model_selection import train_test_split 

from sklearn.ensemble import RandomForestRegressor

X = data['Apparent Temperature (C)'].values

y = data['Humidity'].values

X_train, X_test, y_train, y_test = train_test_split(X,y,test_size = .25, random_state = 2020)

y_train = y_train.reshape(len(y_train),)

y_test = y_test.reshape(len(y_test),)

model = RandomForestRegressor(n_estimators = 100, max_depth = 50 ) 

for train_index, test_index in kf.split(X):

  X_train = X[train_index]
  
  y_train = y[train_index]
  
  X_test = X[test_index]
  
  y_test = y[test_index]
  
  model.fit(X_train, y_train.ravel()) 
  
  y_pred = model.predit(X_test)
  
  PE.append(np.sqrt(MSE(y_test, y_pred)))

#### Question 8: 
def DoKFold(X, y, model, k, rs) : 

  PE1 = [] 
  
  PE2 = []
  
  kf = KFold(n_splits = k, shuffle = True, random_state = 1234) 
  
  for idxtrain,idxtest in kf.split(X): 
  
    Xtrain = X[idxtrain, :]
    
    Xtest = X[idxtest, :]
    
    ytrain = y[idxtrain] 
    
    ytest = y[idxtest]
    
    model.fit(Xtrain, ytrain) 
    
    yhat = model.predict(Xtest) 
    
    PE1.append(MAEf(ytest, yhat)) 
    
    PE2.append(RMSE(ytest,yhat)) 
    
  return np.mean(PE1), np.mean(PE2)
  
X = data[['Humidity', 'Wind Speed (km/h)', 'Pressure (millibars)', 'Wind Bearing (degrees)']].values 

y = df['Temperature (C)'].values

polynomial_features = PolynomialFeatures(degree = 6) 

x_poly = polynomial_features.fit_transform(X) 

model = LinearRegression() 

rmse = np.sqrt(mean_squared_error(y,y_poly_pred)) 

DoKFold(x_poly, y, model, 10, 1234) 


#### Question 9: 

randforest = RandomForestRegressor(n_estimators = 100, max_depth = 50) 

x = data[[''Humidity','Wind Speed (km/h)','Pressure (millibars)','Wind Bearing (degrees)']].values

y = data['Temperature (C)'] 

k = 10 

rs = 1234 

DoKFold(x, y, randforest, k, rs) 

