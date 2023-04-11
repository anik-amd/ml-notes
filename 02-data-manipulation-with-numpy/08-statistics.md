# Analysis

### Minimum & maximum in array

```py
arr = np.array([[0, 72, 3],
                [1, 3, -60],
                [-3, -2, 4]])
print(arr.min())
print(arr.max())

print(repr(arr.min(axis=0)))
print(repr(arr.max(axis=-1)))
```

# Statistical metric

```py
arr = np.array([[0, 72, 3],
                [1, 3, -60],
                [-3, -2, 4]])
print(np.mean(arr))
print(np.var(arr))
print(np.median(arr))
print(repr(np.median(arr, axis=-1)))
```

Find all statistical functions in numpy on [docs](https://numpy.org/doc/stable/reference/routines.statistics.html).

# Reference

- [NumPy Docs](https://numpy.org/doc/stable/)

- [Machine Learning with NumPy, pandas, scikit-learn, and More](https://www.educative.io/courses/machine-learning-numpy-pandas-scikit-learn)
