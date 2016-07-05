---
title: Intro to Data Cleaning
duration: "1:5"
creator:
    name: Lucy Williams
    city: DC
---

# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Intro to Data Cleaning
Week 2 | Lesson 2.3 ..

### LEARNING OBJECTIVES
*After this lesson, you will be able to:*
- Inspect data types
- Clean up a column using `.apply()``
- Know what situations to use `.value_counts()` in your code ..


### LESSON GUIDE
| TIMING  | TYPE  | TOPIC  |
|:-:|---|---|
| 5 min  | [Introduction](#introduction)  | Inspect data types, df.apply(), .value_counts()  |
| 20 min  | [Demo/Guided Practice](#demo)  | Inspect data types |
| 20 min  | [Demo/Guided Practice](#demo)  | df.apply() |
| 20 min  | [Demo/Guided Practice](#demo)  | .value_counts() |
| 20 min  | [Independent Practice](#ind-practice)  |  Practice |
| 5 min  | [Conclusion](#conclusion)  |  Conclusion |

---

<a name="introduction"></a>
## Introduction: Data Type, etc (5 mins)

Since we're starting to get pretty comfortable with using pandas to do EDA, let's add a
couple more tools to our toolbox ..

#### Pandas datatype

The main data types stored in pandas objects are float, int, bool, datetime64, datetime64, timedelta,
category, and object ..

#### apply()

df.apply() will apply a function along any axis of the DataFrame. We'll see it in action below ..

#### value_counts()

`pandas.Series.value_counts` returns Series containing counts of unique values. The resulting
Series will be in descending order so that the first element is the most frequently-occurring
element. Excludes NA values ..

- Examples of [dtypes](http://pandas.pydata.org/pandas-docs/stable/pandas.pdf)

- Examples of [value_counts](http://nullege.com/codes/search/pandas.Series.value_counts)

---

<a name="Inspect data types "></a>
## Demo/Guided Practice: Inspect data types  (20 mins)

Let's create a small dictionary with different data types in it.

in iPython notebook type:
  ```Python
  import pandas as pd
  import numpy as np
  df = pd.DataFrame(dict(A = np.random.rand(3),
                         B = 1,
                         C = 'foo',
                         D = pd.Timestamp('20010102'),
                         E = pd.Series([1.0]*3).astype('float32'),
                         F = False,
                         G = pd.Series([1]*3,dtype='int8')))

  df
  ```
 ..

There is a really easy way to see what kind of `dtypes` are in each column.

<div class="fragment fade-in">
```Python
dft.dtypes
```

If a pandas object contains data multiple `dtypes` **in a single column**, the `dtype` of the
column will be chosen to accommodate all of the data types (object is the most general).

```Python
# these ints are coerced to floats
pd.Series([1, 2, 3, 4, 5, 6.])
```

```Python
# string data forces an ``object`` dtype
pd.Series([1, 2, 3, 6., 'foo'])
```
 ..

The method `get_dtype_counts()` will return the number of columns of each type in a DataFrame:
```Python
dft.get_dtype_counts()
```

You can do a lot more with dtypes that you can check out [here](http://pandas.pydata.org/pandas-docs/stable/pandas.pdf) ..

**Check:** Why do you think it might be important to know what kind of dtypes you're working with?

---

<a name=" df.apply()"></a>
## Demo /Guided Practice:  df.apply() (20 mins) ..

Let's create a small data frame.
<div class="fragment fade-in">
```Python
df = pd.DataFrame(np.random.randn(5, 4), columns=['a', 'b', 'c', 'd'])
df
```
 ..

Use df.apply to find the square root of all the values.

<div class="fragment fade-in">
```Python
df.apply(numpy.sqrt)
```
 ..

Find the mean of all of the columns.
<div class="fragment fade-in">
```Python
df.apply(np.mean, axis=0)
```
  ..

Find the mean of all of the rows.
<div class="fragment fade-in">
```Python
df.apply(np.mean, axis=1)
```
 ..

- [Pandas reciped by Why-Not](https://gist.github.com/why-not/4582705)
- [Applying Operations Over pandas Dataframes - Chris Albon](http://chrisalbon.com/python/pandas_apply_operations_to_dataframes.html)

**Check:** How would find the std of the columns and rows?

---

<a name=".value_counts()"></a>
## Demo /Guided Practice: .value_counts() (20 mins)

Let's create a random array with 50 numbers, ranging from 0 to 7

<div class="fragment fade-in">
```Python
data = np.random.randint(0, 7, size = 50)
```
 ..

Convert the array into a series.

<div class="fragment fade-in">
  ```Python
  s = pd.Series(data)
  ```
 ..

How many of each number is there in the series? Enter value_counts():
<div class="fragment fade-in">
```Python
pd.value_counts(s)
```

---

<a name="ind-practice"></a>
## Independent Practice: Clean up data (20 minutes)

![Cleaning](http://i.giphy.com/kXBVtKjLxINji.gif) ..

- Use the [sales.csv data set](./assets/datasets/sales_info.csv) - we've seen this a few times in previous lessons!
- Inspect the data types
- You've found out that all your values in column 1 are off by 1. Use df.apply to add 1 to column 1 of the dataset
- Use .value_counts to count the values of 1 column of the dataset

**Bonus**
- Add 3 to column 2
- Use .value_counts for each column of the dataset

---

<a name="conclusion"></a>
## Conclusion (5 mins)
So far we've used pandas to look at the head and tail of a data set. We've also taken a look at summary stats and different
types of data types. We've selected and sliced data too. Today we added inspecting data types, df.apply, .value_counts to
our pandas arsenal. Nice!
