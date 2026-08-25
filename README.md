# Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn

## AIM:
To write a program to implement the Decision Tree Classifier Model for Predicting Employee Churn.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Load the employee churn dataset and remove extra spaces from the column names.

2. Encode the categorical features Departments and salary into numerical values.

3. Separate the input features and the target variable left, then split the data into training and testing sets.

4. Train a Decision Tree Classifier using the training data and predict employee churn for the test data.

5. Evaluate the model by comparing predicted and actual values and calculate the accuracy.

## Program:
```
/*
Program to implement the Decision Tree Classifier Model for Predicting Employee Churn.
Developed by:KARANKUMAR K
RegisterNumber:212225040171

import pandas as pd
from sklearn.model_selection import train_test_split
from sklearn.preprocessing import LabelEncoder
from sklearn.tree import DecisionTreeClassifier
from sklearn.metrics import accuracy_score, classification_report

# Load dataset
data = pd.read_csv(r"C:\Users\acer\Downloads\Employee.csv")

# Remove extra spaces from column names
data.columns = data.columns.str.strip()

print("Dataset:")
print(data.head())

print("\nColumn Names:")
print(data.columns.tolist())

# Encode categorical columns
le_department = LabelEncoder()
le_salary = LabelEncoder()

data["Departments"] = le_department.fit_transform(data["Departments"])
data["salary"] = le_salary.fit_transform(data["salary"])

# Separate features and target
X = data.drop("left", axis=1)
y = data["left"]

# Split dataset
X_train, X_test, y_train, y_test = train_test_split(
    X, y,
    test_size=0.2,
    random_state=42
)

# Create Decision Tree Classifier
model = DecisionTreeClassifier(
    criterion="gini",
    max_depth=5,
    random_state=42
)

# Train the model
model.fit(X_train, y_train)

# Predict employee churn
y_pred = model.predict(X_test)

# Calculate accuracy
accuracy = accuracy_score(y_test, y_pred)

print("\nPredicted Values:")
print(y_pred)

print("\nActual Values:")
print(y_test.values)

print("\nAccuracy:", accuracy * 100, "%")

print("\nClassification Report:")
print(classification_report(y_test, y_pred))


 
*/
```

## Output:


<img width="591" height="302" alt="image" src="https://github.com/user-attachments/assets/2f7ea86c-3462-40e7-a5cf-cc9fbb926ced" />



## Result:
Thus the program to implement the  Decision Tree Classifier Model for Predicting Employee Churn is written and verified using python programming.
