# Recommendation system using Item Similarly

# Overview

Building a Recommendation system using Item Similarly as its base.

# Data 

The data used is the MovieLens data set and can be found at below address.
https://grouplens.org/datasets/movielens/


Some other links for datasets are mentioned below.
1. Rating and Classification data from Yahoo

https://webscope.sandbox.yahoo.com/catalog.php?datatype=r

2. Collaborative Filtering Data Set

http://ieor.berkeley.edu/~goldberg/jester-data/

3. Cornell University - Movie - review data for use in sentiment-analysis experiments

http://www.cs.cornell.edu/people/pabo/movie-review-data/

# Usage

The Data for Movie Recommendation (from URL above) is in tab separated format.

We can import such data using Pandas.

```
import pandas as pd
column_names = ['user_id','item_id','rating','timestamp']
df = pd.read_csv('u.data', sep='\t', names=column_names)
```

### Data Exploration

Exploring the Best rated movies

```
import matplotlib.pyplot as plt
import seaborn as sns

```
Create a new datafrome (Rating) with average rating and Number of ratings

- Movies with best average ratings
```
df.groupby('title')['rating'].mean().sort_values(ascending=False)
ratings = pd.DataFrame(df.groupby('title')['rating'].mean())
```

- Movies with most ratings
```
df.groupby('title')['rating'].count().sort_values(ascending=False)
ratings['num of ratings'] = pd.DataFrame(df.groupby('title')['rating'].count())
```

Plot ratings and No of ratings as histograms

rating['rating'].hist(bins=80)

- Relationship between average rating and Number of rating using seaborn Joint plot
sns.jointplot(x='rating',y='num of ratings', data=ratings, aplha=0.5)

- Transforming existing dataframe to get a matrix of user id and movie _title with each cell representing the rating using pivot table

```
movieMatrix = df.pivot_table(index='user_id', columns='title', values='rating')
```

- Comparing corelation between two arbitrary chosen movies

movie 1 = movieMatrix['movie 1 name']
movie 2 = movieMayrix['movie 2 name']

use pandas DataFrame.Corrwith function to compute pairwise correlation between columns of two data frames instead of Index or columns of one data frame. 


