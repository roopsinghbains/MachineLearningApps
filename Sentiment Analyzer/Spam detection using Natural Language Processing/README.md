# Spam detection filter using Natural Language Processing

# Overview

Building a spam detection filter using Natural Language Processing techniques utilizing NLTK library.
The alogrithm used for performing the classfication task is naive bayes. 

## Data 

The data can be obtained from the UCI Machine learning Respoitory.
https://archive.ics.uci.edu/ml/datasets/SMS+Spam+Collection


## Usage

The Data for spam filtering (from URL above) is in tab separated format.

We can import such data using Pandas.

```
import pandas as pd
messages = pd.read_csv('data_path', sep='\t', names=['label','message'])
```
### Data Pre-Processing

As data is in its raw state, it needs to be pre processed before being fed into for training a model.

Some common techniques used.

1. Remove punctuations using pyhton's String module
2. Remove common words which do not provide extra information about the data

Example: Removing stopwords.


```
message = word for word in message.split() if word.lower() not in stopwords.words('English')
```

The above code can be used to perform other data preprocessing tasks such as a technique called stemming also available in the NLTK library. 

### Transforming messages into Bag of Models Representation

#### Pre-requisites

```
from sklearn.feature_extraction.text import CountVectorizer
from sklearn.feature_extraction.text import tfidfTransformer
from sklearn.naive_bayes import MultinomialNB
```

#### Implementation overview


## Fit the above imported modules to desired feature.

#### Transformation library usage sample snippet
```
phase1_featuretransformer = first_TransformInstance.fit(raw_feature)
phase1_transformed_Features = phase1_featuretransformer.transform(raw_feature)

```

Similarly perform further transformations based on data and business problem.

### Transforming
```
tfidfTransformer = tfidfTransformerInstance.fit(data_feature)

feature = transformed_feature.transform(data_feature)
```

### Apply naive bayes
```
spam_detection_model = MultinomialNB.fit(feature,label)

```
