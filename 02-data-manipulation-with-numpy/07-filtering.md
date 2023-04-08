# Filtering data

```py
arr = np.array([[0, 2, 3],
                [1, 3, -6],
                [-3, -2, 1]])
print(repr(arr == 3))
print(repr(arr > 0))
print(repr(arr != 1))
# Negated from the previous step
print(repr(~(arr != 1)))
```

The `~` operation represents a boolean negation, i.e. it flips each truth value in the array.

**Output:**

```py
array([[False, False,  True],
       [False,  True, False],
       [False, False, False]])
array([[False,  True,  True],
       [ True,  True, False],
       [False, False,  True]])
array([[ True,  True,  True],
       [False,  True,  True],
       [ True,  True, False]])
array([[False, False, False],
       [ True, False, False],
       [False, False,  True]])
```

### With `np.nan`

```py
arr = np.array([[0, 2, np.nan],
                [1, np.nan, -6],
                [np.nan, -2, 1]])
print(repr(np.isnan(arr)))
```

**Output:**

```py
array([[False, False,  True],
       [False,  True, False],
       [ True, False, False]])
```

# Filtering in NumPy

### Using `np.where`

`np.where` is a function in the NumPy library that allows you to perform conditional operations on arrays. The syntax of `np.where` is as follows:

```py
np.where(condition[, x, y])
```

The condition parameter is a boolean array that specifies the condition that you want to test. The x parameter is an array or a value that will be returned where `condition` is True. The y parameter is an array or a value that will be returned where `condition` is False. Note that the x and y parameters are optional, and if they are not provided, `np.where` returns the indices of the elements where `condition` is True.

```py
import numpy as np

# create an array
a = np.array([1, 2, 3, 4, 5])

# create a boolean array based on a condition
condition = a > 3

# use np.where to get the indices where the condition is True
indices = np.where(condition)

# print the indices
print(indices)  # output: (array([3, 4]),)
```

# Axis-wise filtering

```py
arr = np.array([[-2, -1, -3],
                [4, 5, -6],
                [3, 9, 1]])
print(repr(arr > 0))
print(np.any(arr > 0))
print(np.all(arr > 0))
```

**Output:**

```py
array([[False, False, False],
       [ True,  True, False],
       [ True,  True,  True]])
True
False
```

Below, function replaces each of the non-positive elements in data with 0. We first create an array of all 0's, with the same shape as data.

Then we filter the data array and replace the non-positive elements with the corresponding element from zeros (which will be a 0).

Set zeros equal to np.zeros_like with data as the lone argument.

Set zero_replace equal to np.where with the condition of data > 0. The second argument will be data and the third argument will be zeros.

Return zero_replace.

```py
def replace_zeros(data):
  # CODE HERE
  zeros = np.zeros_like(data)
  zero_replace = np.where(data > 0, data, zeros)
  return zero_replace
  pass
```

**Output:**

```py
[[19 20  0  0  1],
 [ 9  2  0  0  0],
 [ 0 19 11  2  2],
 [ 1  0  0  0  4]]
```

Broadcasting with `-1`:

```py
def replace_neg_one(data):
  neg_one_replace = np.where(data > 0, data, -1)
  return neg_one_replace
  pass
```

**Output:**

```py
[[19 20 -1 -1  1],
 [ 9  2 -1 -1 -1],
 [-1 19 11  2  2],
 [ 1 -1 -1 -1  4]]
```

### Multidimension arrays

```py
arr = np.array([[-2, -1, -3],
                [4, 5, -6],
                [3, 9, 1]])
print(repr(arr > 0))
print(repr(np.any(arr > 0, axis=0)))
print(repr(np.any(arr > 0, axis=1)))
print(repr(np.all(arr > 0, axis=1)))
```

**Output:**

```py
array([[False, False, False],
       [ True,  True, False],
       [ True,  True,  True]])
array([ True,  True,  True])
array([False,  True,  True])
array([False, False,  True])
```

# Reference

- [NumPy Docs](https://numpy.org/doc/stable/)

- [Machine Learning with NumPy, pandas, scikit-learn, and More](https://www.educative.io/courses/machine-learning-numpy-pandas-scikit-learn)
