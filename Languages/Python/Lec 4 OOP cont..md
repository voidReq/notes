- Alias: When 2 things reference the same object
```python
original: List[int] = [1, 2, 3]
alias: List[int] = original # refers to the same pointer
copy: List[int] = original.copy() # in a different location in computer memory
original[2] = 90 # changes the alias, but not the copy
```

- `__str__()`
	- Every class has one, we usually override
		- The default just has the pointer to the object's location in memory
```Python
	class Cat
	...
	def __str__(self):
		return "your mom"
```
