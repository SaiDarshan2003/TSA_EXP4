## Ex.No:04   FIT ARMA MODEL FOR TIME SERIES
## Date: 

### AIM:
To implement ARMA model in python.
### ALGORITHM:
1. Import necessary libraries.
2. Set up matplotlib settings for figure size.
3. Define an ARMA(1,1) process with coefficients ar1 and ma1, and generate a sample of 1000

data points using the ArmaProcess class. Plot the generated time series and set the title and x-
axis limits.

4. Display the autocorrelation and partial autocorrelation plots for the ARMA(1,1) process using
plot_acf and plot_pacf.
5. Define an ARMA(2,2) process with coefficients ar2 and ma2, and generate a sample of 10000

data points using the ArmaProcess class. Plot the generated time series and set the title and x-
axis limits.

6. Display the autocorrelation and partial autocorrelation plots for the ARMA(2,2) process using
plot_acf and plot_pacf.
### PROGRAM:
```
# Import necessary libraries
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from statsmodels.tsa.arima_process import ArmaProcess
from statsmodels.graphics.tsaplots import plot_acf, plot_pacf
import warnings
warnings.filterwarnings('ignore')
data = pd.read_csv('ECOMM DATA.csv')
profit_data = data['Profit'].dropna()
plt.rcParams['figure.figsize'] = [10, 7.5]
ar1 = np.array([1, 0.33])  # AR(1) coefficient
ma1 = np.array([1, 0.9])   # MA(1) coefficient
ARMA_1 = ArmaProcess(ar1, ma1).generate_sample(nsample=len(profit_data))
plt.plot(ARMA_1)
plt.title('Simulated ARMA(1,1) Process')
plt.xlim([0, 200])
plt.show()
plot_acf(ARMA_1)
plot_pacf(ARMA_1)
ar2 = np.array([1, 0.33, 0.5])  # AR(2) coefficients
ma2 = np.array([1, 0.9, 0.3])   # MA(2) coefficients
ARMA_2 = ArmaProcess(ar2, ma2).generate_sample(nsample=len(profit_data) * 10)
plt.plot(ARMA_2)
plt.title('Simulated ARMA(2,2) Process')
plt.xlim([0, 200])
plt.show()
plot_acf(ARMA_2)
plot_pacf(ARMA_2)

```

OUTPUT:

![image](https://github.com/user-attachments/assets/9e6e39ac-c669-4943-92d3-14bb2253eb65)
![image](https://github.com/user-attachments/assets/e17197a7-eddc-4f03-a043-8661eb38a50e)
![image](https://github.com/user-attachments/assets/38e337fd-1287-4751-8a0c-bfd46f6a2064)




## RESULT:
Thus, a python program is created to fir ARMA Model successfully.
