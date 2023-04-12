# 1D data (aka series)

```py
import pandas as pd
import numpy as np

# Creating an empty series, will result in DeprecationWarning
#series = pd.Series()

# Passing dtype as a parameter to Series for an empty series to avoid DeprecationWarning
# Creating an empty series
series = pd.Series(dtype='float64')
# Newline to separate series print statements
print('{}\n'.format(series))

series = pd.Series(5)
print('{}\n'.format(series))

series = pd.Series([1, 2, 3])
print('{}\n'.format(series))

series = pd.Series([1, 2.2]) # upcasting
print('{}\n'.format(series))

arr = np.array([1, 2])
series = pd.Series(arr, dtype=np.float32)
print('{}\n'.format(series))

series = pd.Series([[1, 2], [3, 4]])
print('{}\n'.format(series))

```

**Output:**

```py

# index    data
# dtype

Series([], dtype: float64)

0    5
dtype: int64

0    1
1    2
2    3
dtype: int64

0    1.0
1    2.2
dtype: float64
```

# Index

Modification of index is possible.

```py
series = pd.Series([1, 2, 3], index=['a', 'b', 'c'])
print('{}\n'.format(series))

series = pd.Series([1, 2, 3], index=['a', 8, 0.3])
print('{}\n'.format(series))
```

**Output:**

```py
a    1
b    2
c    3
dtype: int64

a      1
8      2
0.3    3
dtype: int64
```

# Dictionary input

`key` is the index & `value` is the corresponding value.

```py
series = pd.Series({'a':1, 'b':2, 'c':3})
print('{}\n'.format(series))

series = pd.Series({'b':2, 'a':1, 'c':3})
print('{}\n'.format(series))
```

# Series Operation

### Multiplication

```py
s1 = pd.Series([1,3,5.2])
s2 = s1*[0.1,0.2,0.3]
```
