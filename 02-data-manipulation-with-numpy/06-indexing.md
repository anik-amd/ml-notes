# Array Accessing

```py
arr = np.array([1, 2, 3, 4, 5])
print(arr[0])
print(arr[4])

arr = np.array([[6, 3], [0, 2]])
# Subarray
print(repr(arr[0]))
```

# Slicing

```py
arr = np.array([1, 2, 3, 4, 5])
print(repr(arr[:]))
print(repr(arr[1:]))
print(repr(arr[2:4]))
print(repr(arr[:-1]))
print(repr(arr[-2:]))
```

**Output:**

```py
array([1, 2, 3, 4, 5])
array([2, 3, 4, 5])
array([3, 4])
array([1, 2, 3, 4])
array([4, 5])
```

### Multidimensional Array

```py
arr = np.array([[1, 2, 3],
                [4, 5, 6],
                [7, 8, 9]])
print(repr(arr[:]))
print(repr(arr[1:]))
print(repr(arr[:, -1]))
print(repr(arr[:, 1:]))
print(repr(arr[0:1, 1:]))
print(repr(arr[0, 1:]))
```

**Output:**

```py
array([[1, 2, 3],
       [4, 5, 6],
       [7, 8, 9]])
array([[4, 5, 6],
       [7, 8, 9]])
array([3, 6, 9])
array([[2, 3],
       [5, 6],
       [8, 9]])
array([[2, 3]])
array([2, 3])
```

# Argmin & Argmax

In addition to accessing and slicing arrays, it is useful to figure out the actual indexes of the minimum and maximum elements. To do this, we use the `np.argmin` and `np.argmax` functions.

```py
arr = np.array([[-2, -1, -3],
                [4, 5, -6],
                [-3, 9, 1]])
print(np.argmin(arr[0]))
print(np.argmax(arr[2]))
print(np.argmin(arr))
```

### Axis

The `np.argmin` and `np.argmax` functions take the same arguments. The required argument is the input array, and the axis keyword argument specifies which dimension to apply the operation on.

```py
arr = np.array([[-2, -1, -3],
                [4, 5, -6],
                [-3, 9, 1]])
print(repr(np.argmin(arr, axis=0)))
print(repr(np.argmin(arr, axis=1)))
print(repr(np.argmax(arr, axis=-1)))
```

Note that `axis=0` is column-wise, and `axis=1` is row-wise.

# Reference

- [NumPy Docs](https://numpy.org/doc/stable/)

- [Machine Learning with NumPy, pandas, scikit-learn, and More](https://www.educative.io/courses/machine-learning-numpy-pandas-scikit-learn)
