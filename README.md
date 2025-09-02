# Ex.No: 03   COMPUTE THE AUTO FUNCTION(ACF)
# Date:02.09.2025
# NAME:KEERTHIKA M P
# REG:212223240071

### AIM:
To Compute the AutoCorrelation Function (ACF) of the data for the first 35 lags to determine the model
type to fit the data.
### ALGORITHM:
1. Import the necessary packages
2. Find the mean, variance and then implement normalization for the data.
3. Implement the correlation using necessary logic and obtain the results
4. Store the results in an array
5. Represent the result in graphical representation as given below.
### PROGRAM:
```
import numpy as np
import matplotlib.pyplot as plt
import pandas as pd

df = pd.read_csv('/content/laptop_price.csv', encoding='latin-1')

data = df["Price_euros"].values
N = len(data)

lags = range(40)

autocorr_values = []

mean_data = np.mean(data)
variance_data = np.var(data)
for lag in lags:
    if lag == 0:
        autocorr_values.append(1)
    else:
        auto_cov = np.sum((data[:-lag] - mean_data) * (data[lag:] - mean_data)) / N
        autocorr_values.append(auto_cov / variance_data)

plt.figure(figsize=(10, 6))
plt.stem(lags, autocorr_values)
plt.title('Autocorrelation of Laptop Prices')
plt.xlabel('Lag')
plt.ylabel('Autocorrelation')
plt.grid(True)
plt.show()
```

### OUTPUT:
<img width="1074" height="621" alt="image" src="https://github.com/user-attachments/assets/8e3e81ee-7f14-430c-931e-d75765ac2ec5" />


### RESULT:
        Thus we have successfully implemented the auto correlation function in python.
