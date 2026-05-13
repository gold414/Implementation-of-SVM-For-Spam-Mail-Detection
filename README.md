# Implementation-of-SVM-For-Spam-Mail-Detection

## AIM:
To write a program to implement the SVM For Spam Mail Detection.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Detect File Encoding: Use chardet to determine the dataset's encoding.
2. Load Data: Read the dataset with pandas.read_csv using the detected encoding.
3. Inspect Data: Check dataset structure with .info() and missing values with .isnull().sum().
4. Split Data: Extract text (x) and labels (y) and split into training and test sets using train_test_split.
5. Convert Text to Numerical Data: Use CountVectorizer to transform text into a sparse matrix.
6. Train SVM Model: Fit an SVC model on the training data.
7. Predict Labels: Predict test labels using the trained SVM model.
8. Evaluate Model: Calculate and display accuracy with metrics.accuracy_score.

## Program:
```
Program to implement the SVM For Spam Mail Detection..
Developed by: THANGAPAZHAM P 
RegisterNumber: 212225040469
```
```
import chardet
file='spam.csv'
with open(file, 'rb') as rawdata:
    result = chardet.detect (rawdata.read(100000))
result
```
## Output:

<img width="1183" height="38" alt="image" src="https://github.com/user-attachments/assets/ec007902-8491-4195-ad6c-d0c33df16237" />

## Program:
```
import pandas as pd
data=pd.read_csv('spam.csv', encoding='Windows-1252')
```
```
data.info()
```
## Output:

<img width="1123" height="238" alt="image" src="https://github.com/user-attachments/assets/faf21b05-6325-4f03-a4fb-8c20c0545b19" />

## Program:
```
data.isnull().sum()
```
## Output:

<img width="1141" height="128" alt="image" src="https://github.com/user-attachments/assets/322d2950-6480-40bf-a26c-e2bc436bba9f" />

## Program:
```
x=data["v1"].values
y=data["v2"].values
```
```
from sklearn.model_selection import train_test_split
x_train, x_test, y_train,y_test=train_test_split(x,y,test_size=0.2, random_state=0)
```
```
from sklearn.feature_extraction.text import CountVectorizer
cv = CountVectorizer()
```
```
x_train=cv.fit_transform(x_train)
x_test=cv.transform(x_test)
```
```
from sklearn.svm import SVC
svc=SVC()
svc.fit(x_train, y_train)
y_pred=svc.predict(x_test)
y_pred
```
## Output:

<img width="959" height="100" alt="image" src="https://github.com/user-attachments/assets/3f45eac4-e76b-4c55-9375-177c8fa0cd37" />

## Program:
```
from sklearn import metrics
accuracy=metrics.accuracy_score(y_test,y_pred)
accuracy
```
## Output:

<img width="614" height="53" alt="image" src="https://github.com/user-attachments/assets/0174ab5b-7e49-48ee-8162-8bf4569ab2b9" />

## Result:
Thus the program to implement the SVM For Spam Mail Detection is written and verified using python programming.
