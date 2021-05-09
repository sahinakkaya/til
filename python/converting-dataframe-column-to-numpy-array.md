This returns a numpy array:

```python
arr = df["cluster"].to_numpy()
```

-----

This returns a numpy array of **unique** values:

```python
unique_arr = df["cluster"].unique()
```

You can also use numpy to get the unique values, although there are differences between the two methods([`df.unique`](pandas.pydata.org/pandas-docs/stable/reference/api/pandas.unique.html) doesn't sort while [`np.unique`](numpy.org/devdocs/reference/generated/numpy.unique.html) does):

```python
arr = df["cluster"].to_numpy()
unique_arr = np.unique(arr)
```
