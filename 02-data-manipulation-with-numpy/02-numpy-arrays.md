# Arrays

The code below is an example usage of `np.array` to create a 2-D matrix.

```
import numpy as np

arr = np.array([[0, 1, 2], [3, 4, 5]],
               dtype=np.float32)
# Here np.array takes an array as required argument. Optional dtype argument takes a numpy type (of array).

print(repr(arr))

```

### Type Casting

`int < float < string` in `dtype`.

The code below is an example of `np.array` upcasting. Both integers are cast to their floating-point equivalents.

```
arr = np.array([0, 0.1, 2])
print(repr(arr))

# Output:
# array([0. , 0.1, 2. ])

```

# Copying with reference

```
a = np.array([0, 1])
b = np.array([9, 8])

c = a
# c is a reference to a. Now manupulating c will lead to the same change in a.

print('Array a: {}'.format(repr(a)))
c[0] = 5
print('Array a: {}'.format(repr(a)))

d = b.copy()
# d is a copy of b. Now manupulating d will not change b.

d[0] = 6
print('Array b: {}'.format(repr(b)))
```

# Casting Manually with `astype`

```
arr = np.array([0, 1, 2])
print(arr.dtype)

# Output: int64

arr = arr.astype(np.float32)
print(arr.dtype)

# Output: float32

```

# `nan`

When we don't want a NumPy array to contain a value at a particular index, we can use `np.nan` to act as a placeholder. A common usage for `np.nan` is as a filler value for incomplete data.

The code below shows an example usage of `np.nan`. Note that `np.nan` cannot take on an integer type.

```
arr = np.array([np.nan, 1, 2])
print(repr(arr))

arr = np.array([np.nan, 'abc'])
print(repr(arr))
```

# Infinity

```
print(np.inf > 1000000)

arr = np.array([np.inf, 5]) # Positive infinity with np.inf
print(repr(arr))

arr = np.array([-np.inf, 1]) # Negative infinity with -np.inf
print(repr(arr))
```

Note that `np.inf` cannot take on an integer type.

# Reference

- [NumPy Docs](https://numpy.org/doc/stable/)

- [Machine Learning with NumPy, pandas, scikit-learn, and More](https://www.educative.io/courses/machine-learning-numpy-pandas-scikit-learn)
