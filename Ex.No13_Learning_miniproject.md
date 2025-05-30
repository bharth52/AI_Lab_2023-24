# Ex.No: 10 Learning – Use Supervised Learning  
### DATE: 10/5/2025                                                                          
### REGISTER NUMBER : 212222060023
### AIM: 
To write a program to train the classifier for -----------------.
###  Algorithm:

### Program:
import pandas as pd

from sklearn.linear_model import LinearRegression

from sklearn.metrics import mean_squared_error

import matplotlib.pyplot as plt

df = pd.read_csv('/content/sample_data')

X = df[['input_voltage']]

y = df['el_power']

split_index = int(len(df) * 0.8)

X_train, X_test = X[:split_index], X[split_index:]

y_train, y_test = y[:split_index], y[split_index:]

model = LinearRegression()

model.fit(X_train, y_train)

y_pred = model.predict(X_test)

mse = mean_squared_error(y_test, y_pred)  # Calculate MSE

rmse = mse**0.5  # Calculate RMSE

print(f'RMSE: {rmse:.2f} W')

plt.figure(figsize=(10, 5))

plt.plot(y_test.values, label='Actual')

plt.plot(y_pred, label='Predicted')

plt.legend()

plt.title('Actual vs Predicted Electrical Power')

plt.xlabel('Time')

plt.ylabel('Power (W)')

plt.show()
# output:
![image](https://github.com/user-attachments/assets/a3d9824c-3232-4928-a639-fbf1295ef26e)


### Result:
Thus the system was trained successfully and the prediction was carried out.
