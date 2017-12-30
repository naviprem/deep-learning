# Pandas code snippets

### To display the count of unique values in a series

```bash
df.series.value_counts()
```

Example:

```
kdd_data.num_root.value_counts()
```

Output:

```
0      493435
1         233
9         167
6         126
2          22
5          12
4          10
3           3
119         1
278         1
16          1
268         1
14          1
tcp         1
39          1
857         1
306         1
993         1
12          1
7           1
54          1

```

### Apply a function to a Dataframe:

```bash
df.apply(numpy.sqrt)
df.apply(numpy.sum, axis=0) # equiv to df.sum(0)
df.apply(numpy.sum, axis=1) # equiv to df.sum(1)
```

[https://pandas.pydata.org/pandas-docs/stable/generated/pandas.DataFrame.apply.html](https://pandas.pydata.org/pandas-docs/stable/generated/pandas.DataFrame.apply.html)

### To select a subset of a dataframe by datatype

```bash
df.select_dtypes(include='bool')
df.select_dtypes(include=['float64'])
df.select_dtypes(exclude=['floating'])
```

https://pandas.pydata.org/pandas-docs/stable/generated/pandas.DataFrame.select_dtypes.html


### To encode categorical features

```bash
pd.get_dummies(df_cat.iloc[:,i])], axis=1)
```

### Pandas Options and Settings 

[https://pandas.pydata.org/pandas-docs/stable/options.html](https://pandas.pydata.org/pandas-docs/stable/options.html)



