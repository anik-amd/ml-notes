# Saving

```py
arr = np.array([1, 2, 3])
# Saves to 'arr.npy'
np.save('arr.npy', arr)
# Also saves to 'arr.npy'
np.save('arr', arr)
```

# Loading

```py
arr = np.array([1, 2, 3])
np.save('arr.npy', arr)
load_arr = np.load('arr.npy')
print(repr(load_arr))

# Will result in a FileNotFoundError: If we uncomment line 7 and run again.
#load_arr = np.load('arr')
```
