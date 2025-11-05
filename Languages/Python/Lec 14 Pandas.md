- Normalizing: mapping/scaling
```python
scores = pd.DataFrame({
	'Name': ['Minnie', 'Joe', 'Bob', 'Jeff'],
	'HW1': [4, 6, 5, 6],
	'HW2': [54, 55, 59, 63],
	'HW3': [20, 20, 19, 14],
})

def get_lowest_avg_hw(df: pd.DataFrame) -> str: 
	num_hws = len(df.columns) - 1
	for i in range(1, num_hws+1):
		min = min(df[f'HW{i}'])
		max = max(df[f'HW{i}'])
		df[f'scaled_HW{i}'] = (df[f'HW{i}'] - min) / (max - min)
	df['avg'] = sum([df[f'scaled_HW{i}']]) for i in range (1, num_hws + 1) / num_hws
	min_index = np.argmin(df['avg'])
	return df['Name'][min_index]
	
```

### Merging
- pd.merge() will merge two datasets with one common column
- What if two tables have two of the same column?
	- `pd.merge(df, other_df, 'column to merge with')`
	- If they have differing values within a certain column, merge will just add both columns, with `{column_name}_{df_name}` `{column_name}_{df_name_2}`
- Values that appear in one dataset and not the other, only the ones in both will be included
	- Can use `how` arg
		- `left` -> the first df's rows will be included, and for anything missing on the 2nd df, NaN
		- `right` -> the opposite
		- `outer` -> all rows from both
		- `inner` -> only rows that are in both

```python
await micropip.install("pandas")

df_pricing = pandas.DataFrame({
	'Item': [1, 2, 3, 4, 5],
	'Price': [1, 2, 3, 4, 5]
})

df_purchased = pandas.DataFrame({
	'Item': [1, 2, 3]
})
print(price(pandas.merge(df_pricing, df_purchased, 'right')))
```

- MapReduce:
	- Counting frequency of each word in a piece of text
		- Split the text into words, mapping each word to key/value: (word, 1) pair where word is being mapped. Each word is 1 to start.
	- Reduce phase groups key/value pairs by word, and then adds up the numbers in each group
```python
def mapreduce(documents: List[str]) -> Dict[str, int]:
	mapped = [mapper(doc) for doc in documents]
	shuffled = shuffle(mapped)
	reduced = [reducer(key, values) for key, values in shuffle]
```