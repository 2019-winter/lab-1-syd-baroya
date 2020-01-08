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
a = []
for i in range(0,6):
    new = []
    for j in range(0,4):
        new.append(2)
    a.append(new)
a=np.asarray(a)
print(a) 
```

## Exercise 2

```python
# YOUR SOLUTION HERE
import numpy as np
b = np.eye(6,4)
b=map(lambda x: np.asarray((x*2)+1), b)
b=np.asarray(list(b))
print(b)
```

## Exercise 3

```python
# YOUR SOLUTION HERE
m = a*b
print(m)
# d = np.dot(a,b)
# print(d)
```

The dot product in the above problem does not work because the dimensions of the two matrices do not line up to perform a dot product on them.


## Exercise 4

```python
# YOUR SOLUTION HERE
a_trans = np.dot(a.transpose(), b)
b_trans = np.dot(a, b.transpose())
print("a transposed dot product: ", a_trans)
print("a transposed size: ", np.size(a_trans))
print("b transposed dot product: ", b_trans)
print("b transposed size: ", np.size(b_trans))
```

The results are different sizes because...


## Exercise 5

```python
# YOUR SOLUTION HERE
```

## Exercise 6

```python
# YOUR SOLUTION HERE
```

## Exercise 7

```python
# YOUR SOLUTION HERE
```

## Excercises 8-???
While the Marsland book avoids using another popular package called Pandas, we will use it at times throughout this course. Please read and study [10 minutes to Pandas](https://pandas.pydata.org/pandas-docs/stable/getting_started/10min.html) before proceeding to any of the exercises below.


## Exercise 8
Repeat exercise A.1 from Marsland, but create a Pandas DataFrame instead of a NumPy array.

```python
# YOUR SOLUTION HERE
```

## Exercise 9
Repeat exercise A.2 using a DataFrame instead.

```python
# YOUR SOLUTION HERE
```

## Exercise 10
Repeat exercise A.3 using DataFrames instead.

```python
# YOUR SOLUTION HERE
```

## Exercise 11
Repeat exercise A.7 using a dataframe.

```python
# YOUR SOLUTION HERE
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
```

## Exercise 13
After setting the index to ``sex``, how do you select all passengers that are ``female``? And how many female passengers are there?

```python
## YOUR SOLUTION HERE
titanic_df.set_index('sex',inplace=True)
```

## Exercise 14
How do you reset the index?

```python
## YOUR SOLUTION HERE
```

```python

```
