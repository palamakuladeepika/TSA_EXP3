# Ex.No: 03   COMPUTE THE AUTO CORRELATION FUNCTION(ACF)
Date: 

### AIM:
To Compute the AutoCorrelation Function (ACF) of data for first 35 lags to determine the model type to fit the data.
### ALGORITHM:
1. Import the necessary packages
2. Find the mean, variance and then implement normalization for the data.
3. Implement the correlation using necessary logic and obtain the results
4. Store the results in an array
5. Represent the result in graphical representation as given below.
### PROGRAM:
```
Develped By: Palamakula Deepika
Reg. No.: 212221240035
```
#### Importing Packages:
```python
import matplotlib.pyplot as plt
import numpy as np
```
#### Assigning Data:
```python
data = [3, 16, 156, 47, 246, 176, 233, 140, 130,
        101, 166, 201, 200, 116, 118, 247,209,
        52, 153, 232, 128, 27, 192, 168, 208,
        187, 228, 86, 30, 151, 18, 254,76, 112,
        67, 244, 179, 150, 89, 49, 83, 147, 90,
        33, 6, 158, 80, 35, 186, 127]
lags = range(35)
```

#### Pre-allocate autocorrelation table
```python
autocorr = np.zeros(len(lags))
```
#### Mean
```python
mean = np.mean(data)
```
#### Variance
```python
variance = np.var(data)
```
#### Normalized data
```python
normalized_data = (data - mean) / np.sqrt(variance)
```
#### Go through lag components one-by-one
```python
for i, lag in enumerate(lags):
    if lag == 0:
        autocorr[i] = 1.0
    else:
        autocorr[i] = np.sum(normalized_data[:-lag] * normalized_data[lag:]) / len(data)
```
#### Display the graph
```python
plt.figure(figsize=(10, 5))
plt.stem(lags, autocorr)
plt.title('Autocorrelation')
plt.xlabel('Lag')
plt.ylabel('Autocorrelation')
plt.grid(True)
plt.show()
```
### OUTPUT:

![image](https://github.com/Pavan-Gv/TSA_EXP3/assets/94827772/86f5ee35-d6c1-4214-b6f8-72cb1f34f32e)

### RESULT:
        Thus we have successfully implemented the auto correlation function in python.
