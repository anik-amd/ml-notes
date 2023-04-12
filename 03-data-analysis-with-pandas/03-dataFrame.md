# 2D data

For working with 2-D data, we use the pandas.DataFrame object, which we'll refer to simply as a DataFrame.

```py
df = pd.DataFrame()
# Newline added to separate DataFrames
print('{}\n'.format(df))

df = pd.DataFrame([5, 6])
print('{}\n'.format(df))

df = pd.DataFrame([[5,6]])
print('{}\n'.format(df))

df = pd.DataFrame([[5, 6], [1, 3]],
                  index=['r1', 'r2'],
                  columns=['c1', 'c2'])
print('{}\n'.format(df))

df = pd.DataFrame({'c1': [1, 2], 'c2': [3, 4]},
                  index=['r1', 'r2'])
print('{}\n'.format(df))
```

**Output:**

```py
Empty DataFrame
Columns: []
Index: []

   0
0  5
1  6

   0  1
0  5  6

    c1  c2
r1   5   6
r2   1   3

    c1  c2
r1   1   3
r2   2   4
```

# Upcasting

When we initialize a DataFrame of mixed types, upcasting occurs on a per-column basis. The dtypes property returns the types in each column as a Series of types.

```py
upcast = pd.DataFrame([[5, 6], [1.2, 3]])
print('{}\n'.format(upcast))
# Datatypes of each column
print(upcast.dtypes)
```

**Output:**

```py
     0  1
0  5.0  6
1  1.2  3

0    float64
1      int64
dtype: object
```

# Appending rows

Note that the append function returns the modified DataFrame but doesn't actually change the original. Furthermore, when we append a Series to the DataFrame, we either need to specify the name for the series or use the ignore_index keyword argument. Setting ignore_index=True will change the row labels to integer indexes.

```py
df = pd.DataFrame([[5, 6], [1.2, 3]])
ser = pd.Series([0, 0], name='r3')

df_app = df.append(ser)
print('{}\n'.format(df_app))

df_app = df.append(ser, ignore_index=True)
print('{}\n'.format(df_app))

df2 = pd.DataFrame([[0,0],[9,9]])
df_app = df.append(df2)
print('{}\n'.format(df_app))
```

**Output:**

```py
      0  1
0   5.0  6
1   1.2  3
r3  0.0  0

     0  1
0  5.0  6
1  1.2  3
2  0.0  0

     0  1
0  5.0  6
1  1.2  3
0  0.0  0
1  9.0  9
```

# Dropping Data

```py
df = pd.DataFrame({'c1': [1, 2], 'c2': [3, 4],
                   'c3': [5, 6]},
                  index=['r1', 'r2'])
# Drop row r1
df_drop = df.drop(labels='r1')
print('{}\n'.format(df_drop))

# Drop columns c1, c3
df_drop = df.drop(labels=['c1', 'c3'], axis=1)
print('{}\n'.format(df_drop))

df_drop = df.drop(index='r2')
print('{}\n'.format(df_drop))

df_drop = df.drop(columns='c2')
print('{}\n'.format(df_drop))

df.drop(index='r2', columns='c2')
print('{}\n'.format(df_drop))
```

**Output:**

```py
    c1  c2  c3
r2   2   4   6

    c2
r1   3
r2   4

    c1  c2  c3
r1   1   3   5

    c1  c3
r1   1   5
r2   2   6

    c1  c3
r1   1   5
r2   2   6
```

Similar to append, the drop function returns the modified DataFrame but doesn't actually change the original.
