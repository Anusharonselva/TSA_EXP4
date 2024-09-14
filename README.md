# Ex.No:04   FIT ARMA MODEL FOR TIME SERIES
# Date: 
# Developed  by: ANUSHARON.S
# Register no.: 212222240010


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
import numpy as np
import matplotlib.pyplot as plt
from statsmodels.tsa.arima_process import ArmaProcess
from statsmodels.graphics.tsaplots import plot_acf, plot_pacf

plt.rcParams['figure.figsize'] = (10, 6)

ar1 = np.array([1, -0.5])  # AR(1) coefficient
ma1 = np.array([1, 0.5])   # MA(1) coefficient

arma11_process = ArmaProcess(ar1, ma1)
simulated_data_arma11 = arma11_process.generate_sample(nsample=1000)

plt.plot(simulated_data_arma11)
plt.title('ARMA(1,1) Time Series')
plt.xlabel('Time')
plt.ylabel('Value')
plt.xlim(0, 1000)
plt.grid(True)
plt.show()

plot_acf(simulated_data_arma11, lags=40)
plt.title('ACF of ARMA(1,1)')
plt.show()

plot_pacf(simulated_data_arma11, lags=40)
plt.title('PACF of ARMA(1,1)')
plt.show()

ar2 = np.array([1, -0.3, 0.2])  # AR(2) coefficients
ma2 = np.array([1, 0.4, -0.3])  # MA(2) coefficients

arma22_process = ArmaProcess(ar2, ma2)
simulated_data_arma22 = arma22_process.generate_sample(nsample=10000)

plt.plot(simulated_data_arma22)
plt.title('ARMA(2,2) Time Series')
plt.xlabel('Time')
plt.ylabel('Value')
plt.xlim(0, 10000)
plt.grid(True)
plt.show()

plot_acf(simulated_data_arma22, lags=40)
plt.title('ACF of ARMA(2,2)')
plt.show()

plot_pacf(simulated_data_arma22, lags=40)
plt.title('PACF of ARMA(2,2)')
plt.show()

```

### OUTPUT:
 # SIMULATED ARMA(1,1) PROCESS:

![Screenshot 2024-09-14 093747](https://github.com/user-attachments/assets/360d5c2c-6751-4cc4-8c0a-e0893f25da07)


# Partial Autocorrelation:
![Screenshot 2024-09-14 093938](https://github.com/user-attachments/assets/85e9e92d-1ef8-495e-9790-d1bde54b2ada)


# Autocorrelation:

![Screenshot 2024-09-14 094222](https://github.com/user-attachments/assets/5a3aa9e7-a6f1-4d12-8dc8-f8b72d9f085a)

### SIMULATED ARMA(2,2) PROCESS:
![Screenshot 2024-09-14 093853](https://github.com/user-attachments/assets/bd1f0273-01d3-4a4b-904e-2504adb82035)


# Partial Autocorrelation:
![Screenshot 2024-09-14 094303](https://github.com/user-attachments/assets/7f043b67-3107-4ad6-8109-cb678f7b5580)


# Autocorrelation: 

![Screenshot 2024-09-14 094351](https://github.com/user-attachments/assets/781b8917-6681-47db-a7ff-3cb88ceae357)

### RESULT:
Thus, a python program is created to fir ARMA Model successfully.
