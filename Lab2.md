# Lab 2
### Meredith Webb | Applied Machine Learning | February 21 2021 
#### Question 1: 
k = 8 

(1-1/(k*k))*100

**98.4375%**

#### Question 3: 
mpg_mean = np.mean(mpg)

zs_mpg = (mpg-np.mean(mpg)/np.std(mpg))

print(mpg_mean)

print(np.std(mpg))

zscore18 = (18.1-20.090625000000003)/(5.932029552301218)

print('zscore:', zscore18)
**zscore: -0.335572**
  
#### Question 4: 
qtn = QuantileTransformer(n_quantiles = 100)

weight_percentiles = qtn.fit_transform(data[['wt']])

weight_percentiles[21]

  **/usr/local/lib/python3.6/dist-packages/sklearn/preprocessing/_data.py:2357: UserWarning: n_quantiles (100) is greater than the total number of samples (32). n_quantiles is set to n_samples.
    % (self.n_quantiles, n_samples))**
    
  **array([0.67741935])**
  
  #### Question 6:
x = cars[['wt']]

y = cars[['mpg']]

lm = linear_model.LinearRegression()

model = lm.fit(x,y)

lm.predict([[2.8]])

**22.32** 

#### Question 7: 
def compute_sum(b, m, data):

    total_cost = 0
    
    N = float(len(data))
    

    for i in range(0, len(data)):
        x = data[i, 0]
        y = data[i, 1]
        total_cost += (y - (m * x + b)) ** 2
        

    return total_cost 
    
b, m, cost_graph,b_progress,m_progress = gradient_descent(data, initial_b, initial_m, learning_rate, num_iterations)

print ('Optimized b:', b)
print ('Optimized m:', m)

print ('Minimized sum:', compute_sum(b, m, data))

**278.32**
    
