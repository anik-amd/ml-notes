# Summation

```py
arr = np.array([[0, 72, 3],
                [1, 3, -60],
                [-3, -2, 4]])
print(np.sum(arr))
print(np.sum(arr, axis=0))
print(np.sum(arr, axis=-1))
```

- Cumulative summation can be done with [`np.cumsum`](https://numpy.org/doc/stable/reference/generated/numpy.cumsum.html).

# Concatenation

```py
arr1 = np.array([[0, 72, 3],
                 [1, 3, -60],
                 [-3, -2, 4]])
arr2 = np.array([[-15, 6, 1],
                 [8, 9, -4],
                 [5, -21, 18]])
print(repr(np.concatenate([arr1, arr2])))
print(repr(np.concatenate([arr1, arr2], axis=1)))
print(repr(np.concatenate([arr2, arr1], axis=1)))
```

**Output:**

```py
array([[  0,  72,   3],
       [  1,   3, -60],
       [ -3,  -2,   4],
       [-15,   6,   1],
       [  8,   9,  -4],
       [  5, -21,  18]])
array([[  0,  72,   3, -15,   6,   1],
       [  1,   3, -60,   8,   9,  -4],
       [ -3,  -2,   4,   5, -21,  18]])
array([[-15,   6,   1,   0,  72,   3],
       [  8,   9,  -4,   1,   3, -60],
       [  5, -21,  18,  -3,  -2,   4]])
```
