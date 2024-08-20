# Exno:1
Data Cleaning Process
# R SANJANA
# 212223240148
# AIM
To read the given data and perform data cleaning and save the cleaned data to a file.

# Explanation
Data cleaning is the process of preparing data for analysis by removing or modifying data that is incorrect ,incompleted , irrelevant , duplicated or improperly formatted. Data cleaning is not simply about erasing data ,but rather finding a way to maximize datasets accuracy without necessarily deleting the information.

# Algorithm
STEP 1: Read the given Data

STEP 2: Get the information about the data

STEP 3: Remove the null values from the data

STEP 4: Save the Clean data to the file

STEP 5: Remove outliers using IQR

STEP 6: Use zscore of to remove outliers

# Soft ware required
jupiter notebook

# Coding and Output
```
R.SANJANA
212223240148

import pandas as pd
df =pd.read_csv("SAMPLEIDS.csv")
df.head()
```

![alt text](image.png)

```
df.tail()
```
![alt text](image-1.png)
```
df.info()
```
![alt text](image-2.png)
```
df.describe()
```
![alt text](image-3.png)
```
df.isnull()
```
![alt text](image-4.png)
```
df.isnull().sum()
```
![alt text](image-5.png)
```
df.isnull().any()

```
![alt text](image-6.png)
```
df.dropna()
```
![alt text](image-7.png)
```
df.fillna(0)
```
![alt text](image-8.png)

```
df.fillna(method = 'ffill')
```
![alt text](image-9.png)
```
df.fillna(method = 'bfill')
```
![alt text](image-10.png)
```
df['TOTAL'].fillna(value=df['TOTAL'].mean())
```
![alt text](image-11.png)
```
df_dropped = df.dropna()
df_dropped
```
![alt text](image-12.png)
```
age = [1, 3, 28, 27, 25, 92, 30, 39, 40, 50, 26, 24, 29, 94]
af = pd.DataFrame(age, columns=['Age'])
af
```
![alt text](image-13.png)
```
plt.figure(figsize=(8, 6))
plt.boxplot(af['Age'], vert=False)  # Use 'Age' instead of 'age'
plt.title('Boxplot of Age Data')
plt.xlabel('Age')
plt.grid(axis='x')
plt.show()
```
![alt text](image-14.png)
```
# Filter the DataFrame to remove outliers
af_no_outliers = af[(af['Age'] >= lower_bound) & (af['Age'] <= upper_bound)]

# Display the DataFrame without outliers
print("DataFrame without outliers:")
print(af_no_outliers)
```
![alt text](image-15.png)
```
plt.figure(figsize=(8, 6))
plt.boxplot(af_no_outliers['Age'], vert=False)  # Set vert=False for horizontal boxplot
plt.title('Boxplot of Age Data (Outliers Removed)')
plt.xlabel('Age')
plt.grid(axis='x')
plt.show()
```
![alt text](image-16.png)
```
# Given data
data = [1, 12, 15, 18, 21, 24, 27, 30, 33, 36, 39, 42, 45, 48, 51, 54, 57, 60, 63, 66, 69, 72, 75, 78, 81, 84, 87, 90, 93, 96, 99, 158]
df = pd.DataFrame(data, columns=['Data'])

# Calculate Z-scores
z_scores = stats.zscore(df['Data'])

# Define a threshold for identifying outliers
threshold = 3

# Identify outliers based on Z-scores
outliers = df[np.abs(z_scores) > threshold]

# Display outliers
print("Outliers based on Z-score:")
print(outliers)
```
![alt text](image-17.png)
```
# Create a boxplot
plt.figure(figsize=(8, 6))
plt.boxplot(df['Data'], vert=False)  # Set vert=False for horizontal boxplot
plt.title('Boxplot of Data')
plt.xlabel('Data')
plt.grid(axis='x')
plt.show()
```
![alt text](image-18.png)
```
# Remove outliers from the DataFrame
df_no_outliers = df[np.abs(z_scores) <= threshold]

# Display the DataFrame without outliers
print("DataFrame without outliers:")
print(df_no_outliers)
```
![alt text](image-19.png)
```
plt.subplot(1, 2, 2)
plt.boxplot(df_no_outliers['Data'], vert=False)
plt.title('Boxplot of Data (Outliers Removed)')
plt.xlabel('Data')
plt.grid(axis='x')

plt.tight_layout()
plt.show()
```
![alt text](image-20.png)
# Result
The data cleaning process has been done successfully 
