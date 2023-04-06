# Ranged Data with `np.arange`

```py
arr = np.arange(5)
print(repr(arr))

arr = np.arange(5.1)
print(repr(arr))

arr = np.arange(-1, 4)
print(repr(arr))

arr = np.arange(-1.5, 4, 2)
print(repr(arr))
```

**Output:**

```py
array([0, 1, 2, 3, 4])
array([0., 1., 2., 3., 4., 5.])
array([-1,  0,  1,  2,  3])
array([-1.5,  0.5,  2.5])
```

### Controlling Number of Elements with `np.linspace`

```py
arr = np.linspace(5, 11, num=4)
print(repr(arr))

arr = np.linspace(5, 11, num=4, endpoint=False)
print(repr(arr))

arr = np.linspace(5, 11, num=4, dtype=np.int32)
print(repr(arr))
```

**Output:**

```py
array([ 5.,  7.,  9., 11.])
array([5. , 6.5, 8. , 9.5])
array([ 5,  7,  9, 11], dtype=int32)
```

# Reshaping Data with `np.reshape`

```py
arr = np.arange(8)

reshaped_arr = np.reshape(arr, (2, 4))
print(repr(reshaped_arr))
print('New shape: {}'.format(reshaped_arr.shape))

print("🌧️")

reshaped_arr = np.reshape(arr, (-1, 2, 2))
print(repr(reshaped_arr))
print('New shape: {}'.format(reshaped_arr.shape))
```

**Output:**

```py
array([[0, 1, 2, 3],
       [4, 5, 6, 7]])
New shape: (2, 4)
🌧️
array([[[0, 1],
        [2, 3]],

       [[4, 5],
        [6, 7]]])
```

# Flattening an array with `flatten`

```py
arr = np.arange(8)
arr = np.reshape(arr, (2, 4))
flattened = arr.flatten()
print(repr(arr))
print('arr shape: {}'.format(arr.shape))
print(repr(flattened))
print('flattened shape: {}'.format(flattened.shape))
```

**Output:**

```py
array([[0, 1, 2, 3],
       [4, 5, 6, 7]])
arr shape: (2, 4)
array([0, 1, 2, 3, 4, 5, 6, 7])
flattened shape: (8,)
```

# Transposing with `np.transpose`

```py
arr = np.arange(8)
arr = np.reshape(arr, (4, 2))
transposed = np.transpose(arr)
print(repr(arr))
print('arr shape: {}'.format(arr.shape))
print(repr(transposed))
print('transposed shape: {}'.format(transposed.shape))
```

**Output:**

```py
array([[0, 1],
       [2, 3],
       [4, 5],
       [6, 7]])
arr shape: (4, 2)
array([[0, 2, 4, 6],
       [1, 3, 5, 7]])
transposed shape: (2, 4)
```

### `axis` Argument

`np.transpose` also has a single keyword argument called axes, which represents the new permutation of the dimensions.

The code below shows an example usage of the `np.transpose` function with the axes keyword argument. The shape property gives us the shape of an array.

```py
arr = np.arange(24)
arr = np.reshape(arr, (3, 4, 2))
transposed = np.transpose(arr, axes=(1, 2, 0))
# old dimension -> new dimension
# 0 (first) -> 2 (third)
# 2 (third) -> 1 (second)
# 1 (second) -> 0 (first)
print('arr shape: {}'.format(arr.shape))
print('transposed shape: {}'.format(transposed.shape))
```

The default value for axes is a dimension reversal (e.g. for 3-D data the default `axes` value is [2, 1, 0]).

# Creating arrays with Zeros and Ones

```py
arr = np.zeros(4)
print(repr(arr))

arr = np.ones((2, 3))
print(repr(arr))

arr = np.ones((2, 3), dtype=np.int32)
print(repr(arr))
```

**Output:**

```py
array([0., 0., 0., 0.])
array([[1., 1., 1.],
       [1., 1., 1.]])
array([[1, 1, 1],
       [1, 1, 1]], dtype=int32)
```

### `np.zeros_like` & `np.ones_like`

```py
arr = np.array([[1, 2], [3, 4]])
print(repr(np.zeros_like(arr)))

arr = np.array([[0., 1.], [1.2, 4.]])
print(repr(np.ones_like(arr)))
print(repr(np.ones_like(arr, dtype=np.int32)))
```

**Output:**

```py
array([[0, 0],
       [0, 0]])
array([[1., 1.],
       [1., 1.]])
array([[1, 1],
       [1, 1]], dtype=int32)
```

# Reference

- [NumPy Docs](https://numpy.org/doc/stable/)

- [Machine Learning with NumPy, pandas, scikit-learn, and More](https://www.educative.io/courses/machine-learning-numpy-pandas-scikit-learn)
