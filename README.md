# Ex-04: Compute ACF for the First 35 Lags
## NAME : AMMINENI MOKSHASREE
## REG NO : 2305001001
## Aim
To calculate and plot the Autocorrelation Function (ACF) for the first 35 lags of a time-series dataset and identify a suitable time-series model.

## Objectives
1. To create time-series data using Pandas.
2. To plot the original time series.
3. To calculate ACF values for the first 35 lags.
4. To display and plot the ACF values.
5. To identify possible AR, MA, or ARMA models based on the ACF pattern.

## Program

```
import pandas as pd
import matplotlib.pyplot as plt
from statsmodels.tsa.stattools import acf
from statsmodels.graphics.tsaplots import plot_acf
data = [
    112, 118, 132, 129, 121, 135,
    148, 148, 136, 119, 104, 118,
    115, 126, 141, 135, 125, 149,
    170, 170, 158, 133, 114, 140,
    145, 150, 165, 160, 155, 170,
    190, 188, 175, 160, 145, 165,
    170, 180, 195, 190, 185, 200
]
series = pd.Series(data)
plt.figure(figsize=(10, 4))
plt.plot(series, marker="o")
plt.title("Time Series Data")
plt.xlabel("Time")
plt.ylabel("Value")
plt.grid(True)
plt.show()
acf_values = acf(series, nlags=35)
print("ACF Values:")
for lag, value in enumerate(acf_values):
    print("Lag", lag, ":", round(value, 4))
plt.figure(figsize=(12, 5))
plot_acf(series, lags=35)
plt.title("ACF for First 35 Lags")
plt.xlabel("Lag")
plt.ylabel("Autocorrelation")
plt.show()
```

## Output
<img width="850" height="393" alt="image" src="https://github.com/user-attachments/assets/0a430c94-5831-45ec-9916-c5d0ba2035f7" />
<img width="232" height="657" alt="image" src="https://github.com/user-attachments/assets/924ffe28-3855-4e48-9d31-3cb3eef2b013" />
<img width="587" height="455" alt="image" src="https://github.com/user-attachments/assets/26b9919f-d358-4329-ac46-da93b9ffb118" />


## Result
The Autocorrelation Function (ACF) was successfully calculated and plotted for the first 35 lags. The ACF pattern can help identify a suitable AR, MA, or ARMA model. PACF should also be examined to determine the model order more reliably.
