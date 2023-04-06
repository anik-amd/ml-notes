# Arithmetic

```py
arr = np.array([[1, 2], [3, 4]])
# Add 1 to element values
print(repr(arr + 1))
# Subtract element values by 1.2
print(repr(arr - 1.2))
# Double element values
print(repr(arr * 2))
# Halve element values
print(repr(arr / 2))
# Integer division (half)
print(repr(arr // 2))
# Square element values
print(repr(arr**2))
# Square root element values
print(repr(arr**0.5))
```

**Output:**

```py
array([[2, 3],
       [4, 5]])
array([[-0.2,  0.8],
       [ 1.8,  2.8]])
array([[2, 4],
       [6, 8]])
array([[0.5, 1. ],
       [1.5, 2. ]])
array([[0, 1],
```

### With function

```py
def f2c(temps):
  return (5/9)*(temps-32)

fahrenheits = np.array([32, -4, 14, -40])
celsius = f2c(fahrenheits)
print('Celsius: {}'.format(repr(celsius)))
```

It is important to note that performing arithmetic on NumPy arrays does not change the original array, and instead produces a new array that is the result of the arithmetic operation.

# Non-linear function

```py
arr = np.array([[1, 2], [3, 4]])
# Raised to power of e
print(repr(np.exp(arr)))
# Raised to power of 2
print(repr(np.exp2(arr)))

arr2 = np.array([[1, 10], [np.e, np.pi]])
# Natural logarithm
print(repr(np.log(arr2)))
# Base 10 logarithm
print(repr(np.log10(arr2)))
```

### Power Operations

```py
arr = np.array([[1, 2], [3, 4]])
# Raise 3 to power of each number in arr
print(repr(np.power(3, arr)))
arr2 = np.array([[10.2, 4], [3, 5]])
# Raise arr2 to power of each number in arr
print(repr(np.power(arr2, arr)))
```

**Output:**

```py
array([[ 3,  9],
       [27, 81]])
array([[ 10.2,  16. ],
       [ 27. , 625. ]])
```

All mathematical function of NumPy is [available on docs](https://numpy.org/doc/stable/reference/routines.math.html).

# Matrix Multiplication

```py
arr1 = np.array([1, 2, 3])
arr2 = np.array([-3, 0, 10])
print(np.matmul(arr1, arr2))
#  np.matmul takes two vector/matrix arrays as input and produces a dot product or matrix multiplication.

arr3 = np.array([[1, 2], [3, 4], [5, 6]])
arr4 = np.array([[-1, 0, 1], [3, 2, -4]])
print(repr(np.matmul(arr3, arr4)))
print(repr(np.matmul(arr4, arr3)))
# The second dimension of the first matrix must equal the first dimension of the second matrix, otherwise np.matmul will result in a ValueError.
# This will result in a ValueError: If we uncomment line 10 and run again.
#print(repr(np.matmul(arr3, arr3)))
```
