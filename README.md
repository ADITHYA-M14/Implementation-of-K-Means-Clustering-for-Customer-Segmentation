# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import the standard libraries.
2. Upload the dataset and check for any null values using .isnull() function. 
3. Import LabelEncoder and encode the dataset.
4. Import DecisionTreeRegressor from sklearn and apply the model on the dataset.
5. Predict the values of arrays.
6. Import metrics from sklearn and calculate the MSE and R2 of the model on the dataset.
7. Predict the values of array.
8. Apply to new unknown values.

## Program:
```
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: ADITHYA M
RegisterNumber: 212224230008
```
```
import pandas as pd
import matplotlib.pyplot as plt
from sklearn.tree import DecisionTreeClassifier, plot_tree
data = pd.read_csv("Salary_EX7.csv")
data.head()
data.info()
data.isnull().sum()
from sklearn.preprocessing import LabelEncoder
le = LabelEncoder()
data["Position"] = le.fit_transform(data["Position"])
data.head()
x=data[["Position","Level"]]
y=data["Salary"]
from sklearn.model_selection import train_test_split
x_train, x_test, y_train, y_test = train_test_split(x,y,test_size=0.2,random_state=2)
from sklearn.tree import DecisionTreeRegressor,plot_tree
dt=DecisionTreeRegressor()
dt.fit(x_train,y_train)
y_pred=dt.predict(x_test)
from sklearn import metrics
mse = metrics.mean_squared_error(y_test,y_pred)
mse
r2=metrics.r2_score(y_test,y_pred)
r2
dt.predict(pd.DataFrame([[5,6]], columns=x.columns))
plt.figure(figsize=(20, 8))
plot_tree(dt, feature_names=list(x.columns), filled=True)
plt.show()
```
## Output:

## Data Head :
<img width="425" height="292" alt="image" src="https://github.com/user-attachments/assets/0fb15f6e-5b4d-444b-8e9b-d9cf3d900e9f" />

## Data Info :
<img width="413" height="259" alt="image" src="https://github.com/user-attachments/assets/46288728-82cb-4838-b41b-2fb86c4aac9e" />

## Data Details :
<img width="525" height="632" alt="image" src="https://github.com/user-attachments/assets/eec7ef0b-1f19-4e68-b5a6-84ef9d60464a" />

## Data Predcition :
<img width="1218" height="447" alt="image" src="https://github.com/user-attachments/assets/76835aa5-73c5-45aa-b674-f8c41187ea01" />

## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
