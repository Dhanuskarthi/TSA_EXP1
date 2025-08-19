# Ex.No: 01A PLOT A TIME SERIES DATA
###  Date: 

# AIM:
To Develop a python program to Plot a time series data (population/ market price of a commodity
/temperature.
# ALGORITHM:
1. Import the required packages like pandas and matplot
2. Read the dataset using the pandas
3. Calculate the mean for the respective column.
4. Plot the data according to need and can be altered monthly, or yearly.
5. Display the graph.
# PROGRAM:
```
import pandas as pd
import matplotlib.pyplot as plt

file_path = '/content/Time-Series Analysis Dataset.csv'
data = pd.read_csv(file_path)

data['datetime_local'] = pd.to_datetime(data['datetime_local'], dayfirst=True)
data.set_index('datetime_local', inplace=True)

plt.figure(figsize=(10, 6))
plt.plot(data.index, data['temperature'], label='Temperature', color='blue')
plt.title('Temperature Over Time')
plt.xlabel('Datetime')
plt.ylabel('Temperature (°C)')
plt.grid(True)
plt.legend()
plt.show()

plt.figure(figsize=(10, 6))
plt.hist(data['temperature'], bins=30, color='skyblue', edgecolor="black")
plt.title('Temperature Distribution')
plt.xlabel('Temperature (°C)')
plt.ylabel('Frequency')
plt.show()

selected_columns = ['humidity', 'dew_point', 'wind_bearing', 
                    'wind_speed','wind_gust','pressure','precip_intensity']

data[selected_columns].plot(kind='line', figsize=(15, 8))
plt.title('Line Plot for Selected Weather Columns')
plt.xlabel('Datetime')
plt.ylabel('Values')
plt.legend(loc='upper left')
plt.show()

```







# OUTPUT:

<img width="1039" height="661" alt="Screenshot 2025-08-19 091001" src="https://github.com/user-attachments/assets/e1b6395f-d812-4914-8294-0c9a59c7d37b" />


<img width="1022" height="682" alt="Screenshot 2025-08-19 091011" src="https://github.com/user-attachments/assets/dbf9dc9a-253d-4b49-a418-33291a164d86" />



<img width="1379" height="744" alt="Screenshot 2025-08-19 091027" src="https://github.com/user-attachments/assets/e95cb60c-46ab-43ac-a678-33165de7f837" />



# RESULT:
Thus we have created the python code for plotting the time series of given data.
