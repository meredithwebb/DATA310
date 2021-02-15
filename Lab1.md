# Lab 1
#### Meredith Webb | Applied Machine Learning | February 15 2021
## Question Two
### Importing the Data:
![Figure 1](https://meredithwebb.github.io/DATA310/Question2.png)
### Imputation for replacing the NaN values in the "Age" column with the median of the column:
![Figure 2](https://meredithwebb.github.io/DATA310/Question22.png)
## Question Five: 
If 30% of the people infected with the virus are asymtomatic, then 70% of them are symptomatic. Knowing this, I multiplied .70 by .15 and then divided that value by .35, which is the percentage of the population with general respiratory symptoms to get an answer of 30%
## Question Eight: 
%matplotlib inline
%config InlineBackend.figure_format = 'retina'
import matplotlib as mpl
mpl.rcParams['figure.dpi'] = 150

import random
import matplotlib.pyplot as plt

doors = ["goat","goat","car", "goat"]

switch_win_probability = []
stick_win_probability = []

plt.axhline(y=0.66, color='red', linestyle='--')
plt.axhline(y=0.33, color='green', linestyle='--')

def monte_carlo(n):

  switch_wins = 0
  stick_wins = 0

  for i in range(n):
     random.shuffle(doors)

      k = random.randrange(4)

     if doors[k] != 'car':
       switch_wins +=1
    
     else:
       stick_wins +=1
    
     switch_win_probability.append(switch_wins/(i+1))
     stick_win_probability.append(stick_wins/(i+1))

  print('Winning probability if you always switch:', switch_win_probability[-1])
  print('Winning probability if you always stick to your original choice:', stick_win_probability[-1])

monte_carlo(3000)

