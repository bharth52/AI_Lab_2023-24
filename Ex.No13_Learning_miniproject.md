# Ex.No: 13 Learning – Use Supervised Learning(Miniproject)
## DATE:     
4.11.2024
## REGISTER NUMBER : 
212222040106
## AIM: 
To write a program to train the classifier for Student Exam Performance Prediction.
##  Algorithm:
Step 1 : Start the program.<br>
Step 2 : Import the necessary packages, such as NumPy, Pandas, Matplotlib, and Seaborn.<br>
Step 3 : Install and import Gradio for creating the user interface.<br>
Step 4 : Load the student performance dataset using Pandas.<br>
Step 5 : Perform exploratory data analysis (EDA) and visualize the data (optional).<br>
Step 6 : Check for missing values and handle them if necessary.<br>
Step 7 : Encode categorical features using LabelEncoder or OneHotEncoder.<br>
Step 8 : Split the dataset into input features (X) and target labels (y).<br>
Step 9 : Split the data into training and testing sets using train_test_split.<br>
Step 10 : Standardize the training and testing data using StandardScaler.<br>
Step 11 : Instantiate the MLPClassifier model with 1000 iterations and train the model on the training data.<br>
Step 12 : Print the model's accuracy on both the training and testing sets.<br>
Step 13 : Create a Gradio interface to take input values for student features and predict the exam performance using the trained model.<br>
Step 14 : Launch the Gradio interface for user interaction.<br>
Step 15 : Stop the program.<br>

## Program:
```
import numpy as np # linear algebra
import pandas as pd # data processing, CSV file I/O (e.g. pd.read_csv)


import os
for dirname, _, filenames in os.walk('/kaggle/input'):
    for filename in filenames:
        print(os.path.join(dirname, filename))


data = pd.read_csv('/content/sample_data/student_exam_data.csv')
data.head()

data.dtypes

data.shape

data.columns

X = data.drop(['Pass/Fail'], axis=1)
y = data['Pass/Fail']

from sklearn.model_selection import train_test_split

X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.3, random_state=42)

from sklearn.preprocessing import MinMaxScaler

scale = MinMaxScaler()

X_train_scale = scale.fit_transform(X_train)
X_test_scale = scale.transform(X_test)

from sklearn.ensemble import RandomForestClassifier
model = RandomForestClassifier()

from sklearn.metrics import accuracy_score

model.fit(X_train_scale, y_train)

y_pred = model.predict(X_test_scale)

print("Accuracy:", accuracy_score(y_test, y_pred))
```

### Output:

![ai-mini1](https://github.com/user-attachments/assets/16d96d93-4601-44d9-869a-db087fb9acd3)
![ai-mini2](https://github.com/user-attachments/assets/66a743a2-5e4c-4b1d-a6ee-c7145900df07)
![ai-mini3](https://github.com/user-attachments/assets/2faf6265-919b-4196-aaa0-f2aa2cbabd62)




### Result:
Thus the system was trained successfully and the prediction was carried out.

