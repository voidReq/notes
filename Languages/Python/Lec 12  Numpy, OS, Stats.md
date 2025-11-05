# Numpy
```python
data = {
	'title': ['The Matrix', 'Inception', 'Interstellar', 'Blade Runner'],
	'year': [1999, 2000, 2001, 2003, 1984],
	'rating': [8.7, 8.8, 8.6, 4.0, 5.6]
}
df=pd.DataFrame(data)
# print(np.mean(df['rating']))
for index, row in df.iterrows():
	print(f'{row["title"]} was released in 1999')
```
to add a row, create another dataframe and concatenate
```python
new_movie = pd.DataFrame({
	'title': ['Dune'],
	'year': [2021],
	'rating': [8.0]
})
df = pd.concat([df, new_row], ignore_index=True)
```
to add a column:
```python
df_people = pd.DataFrame({
	'Person': []
})
```

Raising Errors:
```python
raise BlahBlahError
```

# OS
```python
os.path.exists("path/file")
os.path.join("base/path", 'name')
os.listdir('path/dir')
```

# Statistics

- Correlation: When two variables appear to be related in some way
- Find correlation coeff:
```python
df = pd.DataFrame({
	'age': [13, 19, 3],
})
print(np.corrcoef(df['age'], df['Height']))
"""

"""
#corrcoef provides the following:
"""
[[corr(x,x)], corr(x,y)]
[corr(y,x)], corr(y,y)]]
"""

```

- Histograms: 1 variable
- Bar graphs, scatterplots: 2 variables