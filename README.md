# Implementation-of-SVM-For-Spam-Mail-Detection

## AIM:
To write a program to implement the SVM For Spam Mail Detection.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
Step 1: Import the required packages.

Step 2: Import the dataset to operate on.

Step 3: Split the dataset.

Step 4: Predict the required output. 

## Program:
```
/*
Program to implement the SVM For Spam Mail Detection..
Developed by: SURESH S
RegisterNumber: 212223040215
*/
```
```
import pandas as pd
data=pd.read_csv('/content/spam.csv',encoding='Windows-1252')
```
```
data.head()
```

![image](https://github.com/user-attachments/assets/c88e8a9a-003b-465b-8492-4969439ebf5d)

```
data.tail()
```

![image](https://github.com/user-attachments/assets/0e69b728-55ab-43b7-bcfb-141c0ee64cc6)


```
data.info()
```

![image](https://github.com/user-attachments/assets/824ed749-e06e-4d45-96d4-cc04b16748ed)

```
data.isnull().sum()
```

![image](https://github.com/user-attachments/assets/01ec74d7-1250-49b4-aa4a-5339eb5b8dc5)

```
x=data["v2"].values
y=data["v1"].values
```

```
x.shape
```

![image](https://github.com/user-attachments/assets/75a0355b-45af-4f0f-a249-7c906795a2cc)

```
y.shape
```

![image](https://github.com/user-attachments/assets/50405ad1-1137-41fc-a0e6-ffb418498c01)

```
from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.2,random_state=0)
```

```
x_train.shape
```

![image](https://github.com/user-attachments/assets/d8ca04cf-eda9-4785-8400-1013d9ed519f)

```
y_train.shape
```

![image](https://github.com/user-attachments/assets/addfc677-b30f-4669-ab7a-2e589711b7f4)




```
x_test.shape
```


 ![image](https://github.com/user-attachments/assets/6cf2a738-483e-4463-be1a-75d8125826a7)



y_test.shape
```



```
from sklearn.feature_extraction.text import CountVectorizer
cv=CountVectorizer()
x_train=cv.fit_transform(x_train)
x_test=cv.transform(x_test)
```
```
type(x_train)
```

![image](https://github.com/user-attachments/assets/eab16e10-b2dc-4ebe-b89d-c5afb1ce13dd)

```
from sklearn.svm import SVC
svc=SVC()
svc.fit(x_train,y_train)
y_pred=svc.predict(x_test)
y_pred
```

![image](https://github.com/user-attachments/assets/cc126cbe-342a-4754-8c29-ce1e1ca1e80b)

```
from sklearn.metrics import accuracy_score
accuracy_score(y_test,y_pred)
```

![image](https://github.com/user-attachments/assets/3669a1e6-6284-4dc9-871d-ec8fdf581a2b)




## Result:
Thus the program to implement the SVM For Spam Mail Detection is written and verified using python programming.
