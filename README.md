# Implementation-of-SVM-For-Spam-Mail-Detection

## AIM:
To write a program to implement the SVM For Spam Mail Detection.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm

1.Import the necessary python packages using import statements.

2.Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().

3.Split the dataset using train_test_split.

4.Calculate Y_Pred and accuracy.

5.Print all the outputs.

6.End the Program.

## Program:
```
/*
Program to implement the SVM For Spam Mail Detection..
Developed by: THIRISHA A
RegisterNumber:  212223040228
*/
```
```
import chardet
file='spam.csv'
with open (file,'rb') as rawdata:
    result = chardet.detect(rawdata.read(100000))
result
import pandas as pd
data=pd.read_csv("spam.csv",encoding='windows-1252')
data.head()
```

![Screenshot 2025-05-17 140847](https://github.com/user-attachments/assets/4b437dec-22d2-4a4c-8086-2449be94d118)
```
data.info()
```

![Screenshot 2025-05-17 140855](https://github.com/user-attachments/assets/e4fb1ce3-5126-41eb-9d00-394dbfd81943)
```
data.isnull().sum()
```
![Screenshot 2025-05-17 140901](https://github.com/user-attachments/assets/a8cc2c50-aac1-43c6-9965-0b056c83ebac)
```
x=data["v1"].values
y=data["v2"].values
from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.2,random_state=0)
from sklearn.feature_extraction.text import CountVectorizer
cv=CountVectorizer()
x_train=cv.fit_transform(x_train)
x_test=cv.transform(x_test)
from sklearn.svm import SVC
svc=SVC()
svc.fit(x_train,y_train)
y_pred=svc.predict(x_test)
y_pred
```
![Screenshot 2025-05-17 141837](https://github.com/user-attachments/assets/348a77c3-a548-40a2-ad4d-892e5e74cd3b)

```
from sklearn import metrics
accuracy=metrics.accuracy_score(y_test,y_pred)
accuracy
```
![Screenshot 2025-05-17 141845](https://github.com/user-attachments/assets/09edac98-e0e2-40a0-a595-e63020f6eab4)

## Result:
Thus the program to implement the SVM For Spam Mail Detection is written and verified using python programming.
