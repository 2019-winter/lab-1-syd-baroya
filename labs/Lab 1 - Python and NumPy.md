---
jupyter:
  jupytext:
    formats: ipynb,md
    text_representation:
      extension: .md
      format_name: markdown
      format_version: '1.1'
      jupytext_version: 1.2.4
  kernelspec:
    display_name: Python 3
    language: python
    name: python3
---

# Name(s)
**Sydney Baroya**


**Instructions:** This is an individual assignment, but you may discuss your code with your neighbors.


# Python and NumPy

While other IDEs exist for Python development and for data science related activities, one of the most popular environments is Jupyter Notebooks.

This lab is not intended to teach you everything you will use in this course. Instead, it is designed to give you exposure to some critical components from NumPy that we will rely upon routinely.

## Exercise 0
Please read and reference the following as your progress through this course. 

* [What is the Jupyter Notebook?](https://nbviewer.jupyter.org/github/jupyter/notebook/blob/master/docs/source/examples/Notebook/What%20is%20the%20Jupyter%20Notebook.ipynb#)
* [Notebook Tutorial](https://www.datacamp.com/community/tutorials/tutorial-jupyter-notebook)
* [Notebook Basics](https://nbviewer.jupyter.org/github/jupyter/notebook/blob/master/docs/source/examples/Notebook/Notebook%20Basics.ipynb)

**In the space provided below, what are three things that still remain unclear or need further explanation?**


**YOUR ANSWER HERE**


## Exercises 1-7
For the following exercises please read the Python appendix in the Marsland textbook and answer problems A.1-A.7 in the space provided below.


## Exercise 1

```python
# YOUR SOLUTION HERE
import numpy as np
a = np.ones((6,4)) * 2
print(a) 
```

## Exercise 2

```python
# YOUR SOLUTION HERE
b = np.ones((6,4))
np.fill_diagonal(b, 3)
print(b)
```

## Exercise 3

```python
# YOUR SOLUTION HERE
m = a*b
print(m)
# d = np.dot(a,b)
# print(d)
print("\"a\" is a 6x4 array")
print("\"b\" is a 6x4 array")
print("for a dot product to work with these arrays, the second dimension of \"a\" and the first dimension of \"b\" must be the same number.")
print("(i.e. \"a\" is a 6x4 array and \"b\" is a 4x6 array)")
```

## Exercise 4

```python
# YOUR SOLUTION HERE
a_trans = np.dot(a.transpose(), b)
b_trans = np.dot(a, b.transpose())
print("a transposed dot product: ", a_trans)
print("b transposed dot product: ", b_trans)
print("the dot product with the transposed \"a\" matrix results in a 4x4 matrix because the product is between a 4x6 and 6x4 matrix")
print("the dot product with the transposed \"a\" matrix results in a 6x6 matrix because the product is between a 6x4 and 4x6 matrix")
```

## Exercise 5

```python
# YOUR SOLUTION HERE
def func():
    print("hello")

func()
```

## Exercise 6

```python
# YOUR SOLUTION HERE
def rand_array_data(num_of_arrays, dim1, dim2):
    for i in range(num_of_arrays):
        a = np.random.rand(dim1, dim2)
        print("array ", i+1, ": ", a)
        print("sum: ", np.sum(a))
        print("mean value: ", np.mean(a))
        print("median: ", np.median(a))

rand_array_data(1, 6, 4)
rand_array_data(4, 3, 1)
```

## Exercise 7

```python
# YOUR SOLUTION HERE
def find_ones_loops(arr):
    counter = 0
    for x in arr:
        try:
            for y in x:
                if y==1:
                    counter += 1
        except TypeError:
            if x==1:
                    counter += 1
    return counter

def find_ones_where(arr):
    return np.sum(np.where(arr == 1, 1, 0))

f1 = find_ones_loops(np.array([3, 2, 1, 6, 1]))
f2 = find_ones_loops(np.array([[3, 2, 1], [6, 1, 5], [1, 2, 1]]))
print(f1)
print(f2)

f3 = find_ones_where(np.array([3, 2, 1, 6, 1]))
f4 = find_ones_where(np.array([[3, 2, 1], [6, 1, 5], [1, 2, 1]]))
print(f3)
print(f4)
```

## Excercises 8-???
While the Marsland book avoids using another popular package called Pandas, we will use it at times throughout this course. Please read and study [10 minutes to Pandas](https://pandas.pydata.org/pandas-docs/stable/getting_started/10min.html) before proceeding to any of the exercises below.


## Exercise 8
Repeat exercise A.1 from Marsland, but create a Pandas DataFrame instead of a NumPy array.

```python
# YOUR SOLUTION HERE
import pandas as pd
a2 = pd.DataFrame(np.ones((6,4)) * 2)
print(a2)
```

## Exercise 9
Repeat exercise A.2 using a DataFrame instead.

```python
# YOUR SOLUTION HERE
tempb = np.ones((6,4))
np.fill_diagonal(tempb, 3)
b2 = pd.DataFrame(tempb)
print(b2)
```

## Exercise 10
Repeat exercise A.3 using DataFrames instead.

```python
# YOUR SOLUTION HERE
m = a2*b2
print(m)
# d = np.dot(a,b)
# print(d)
print("\"a2\" is a 6x4 array")
print("\"b2\" is a 6x4 array")
print("for a dot product to work with these arrays, the second dimension of \"a2\" and the first dimension of \"b2\" must be the same number.")
print("(i.e. \"a2\" is a 6x4 array and \"b2\" is a 4x6 array)")
```

## Exercise 11
Repeat exercise A.7 using a dataframe.

```python
# YOUR SOLUTION HERE
def find_ones_loops(df):
    counter=0
    for index, row in df.iterrows(): 
        for x in range(len(row)):
            if row[x]==1:
                counter+=1
    return counter

def find_ones_where(arr):
    return np.sum(np.where(arr == 1, 1, 0))

f1 = find_ones_loops(a2)
f2 = find_ones_loops(b2)
print(f1)
print(f2)

f3 = find_ones_where(a2)
f4 = find_ones_where(b2)
print(f3)
print(f4)
```

## Exercises 12-14
Now let's look at a real dataset, and talk about ``.loc``. For this exercise, we will use the popular Titanic dataset from Kaggle. Here is some sample code to read it into a dataframe.

```python
titanic_df = pd.read_csv(
    "https://raw.githubusercontent.com/dlsun/data-science-book/master/data/titanic.csv"
)
titanic_df
```

Notice how we have nice headers and mixed datatypes? That is one of the reasons we might use Pandas. Please refresh your memory by looking at the 10 minutes to Pandas again, but then answer the following.


## Exercise 12
How do you select the ``name`` column without using .iloc?

```python
## YOUR SOLUTION HERE
titanic_df.loc[:,'name']
```

## Exercise 13
After setting the index to ``sex``, how do you select all passengers that are ``female``? And how many female passengers are there?

```python
## YOUR SOLUTION HERE
titanic_df.set_index('sex',inplace=True)
female = titanic_df.loc['female']
print(female)
print(len(female.index))
```

## Exercise 14
How do you reset the index?

```python
## YOUR SOLUTION HERE
titanic_df.reset_index()
```
