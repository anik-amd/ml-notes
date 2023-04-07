# Random Integers

```py
print(np.random.randint(5))
print(np.random.randint(5))
print(np.random.randint(5, high=6))

random_arr = np.random.randint(-3, high=14,
                               size=(2, 2))
print(repr(random_arr))
```

The `np.random.randint` function takes in a single required argument, which actually depends on the high keyword argument. If high=None (which is the default value), then the required argument represents the upper (exclusive) end of the range, with the lower end being 0. Specifically, if the required argument is n, then the random integer is chosen uniformly from the range `[0, n)`.

If high is not None, then the required argument will represent the lower (inclusive) end of the range, while high represents the upper (exclusive) end.

The size keyword argument specifies the size of the output array, where each integer in the array is randomly drawn from the specified range. As a default, `np.random.randint` returns a single integer.

# Utility Functions

### Seeding

```py
np.random.seed(1)
print(np.random.randint(10))
random_arr = np.random.randint(3, high=100,
                               size=(2, 2))
print(repr(random_arr))

# New seed
np.random.seed(2)
print(np.random.randint(10))
random_arr = np.random.randint(3, high=100,
                               size=(2, 2))
print(repr(random_arr))

# Original seed
np.random.seed(1)
print(np.random.randint(10))
random_arr = np.random.randint(3, high=100,
                               size=(2, 2))
print(repr(random_arr))
```

**Output:**

```py
5
array([[15, 75],
       [12, 78]])
8
array([[18, 75],
       [25, 46]])
5
array([[15, 75],
       [12, 78]])
```

### Shuffle

```py
vec = np.array([1, 2, 3, 4, 5])
np.random.shuffle(vec)
print(repr(vec))
np.random.shuffle(vec)
print(repr(vec))

matrix = np.array([[1, 2, 3],
                   [4, 5, 6],
                   [7, 8, 9]])
np.random.shuffle(matrix)
print(repr(matrix))
```

`np.random.shuffle` function allows us to randomly shuffle an array. Note that the shuffling happens in place (i.e. no return value), and shuffling multidimensional arrays only shuffles the first dimension.

# Distributions

- [`np.random.uniform`](https://docs.scipy.org/doc/numpy-1.14.0/reference/generated/numpy.random.uniform.html#numpy.random.uniform)
- [`np.random.normal`](https://docs.scipy.org/doc/numpy-1.14.0/reference/generated/numpy.random.normal.html#numpy.random.normal)
- [All built-in distributions](https://docs.scipy.org/doc/numpy-1.14.1/reference/routines.random.html)

# Custom Sampling

```py
colors = ['red', 'blue', 'green']
print(np.random.choice(colors))
print(repr(np.random.choice(colors, size=2)))
print(repr(np.random.choice(colors, size=(2, 2),
                            p=[0.8, 0.19, 0.01])))
```

**Output:**

```py
red
array(['green', 'red'], dtype='<U5')
array([['red', 'red'],
       ['blue', 'red']], dtype='<U5')
```

Note that the list of probabilities for `p` must sum to 1.

# Reference

- [NumPy Docs](https://numpy.org/doc/stable/)

- [Machine Learning with NumPy, pandas, scikit-learn, and More](https://www.educative.io/courses/machine-learning-numpy-pandas-scikit-learn)
