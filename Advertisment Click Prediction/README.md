# Logistic Regression

# Overview

Building a advertisement click prediction solution providing predictions
whether a user will click on an advertisement based of features of the user.

# Data 

The data contains information about the user for example age, income, ad topic line etc.

# Usage

We can import such data using Pandas.

```
import pandas as pd
ad_data = pd.read_csv('ad.csv')
```

### Data Exploration

Exploring the head of data as first step

```
ad_data.head()
ad_data.info()
ad_data.describe()

```

```
import matplotlib.pyplot as plt
import seaborn as sns

```

Plot seaborn joint plot of Time spent and age

```
sns.jointplot(x='Age', y='Daily Time spent on Site', data=ad_data;kind='kde')
```

# Logistic Regression

Split data into Training and Test Set

```
from sklearn.cross_validation import train_test_split
X_train, X_test, y_train, y_test = train_test_split(X,y,test_size=0.3)
```

```
from sklearn.linear_model import LogisticRegression
logisticmodel = LogisticRegression()
logisticmodel.fit(X_train,y_train)
```

## Predictions and Evaluation

```
predictions = logisticmodel.predict(X_test)
```
### Classification report

```
from sklearn.metrics import Classification_report, Confusion_matrix
Classification_report(y_test,predictions)
Confusion_matrix(y_test,predictions)
```


