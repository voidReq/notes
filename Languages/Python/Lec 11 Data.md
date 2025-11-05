- Containers (list, tuples)
	- Store references to objects
		- More space, slower
		- Can have varying types
- Flat sequences
	- Raw values in consecutive memory locations
	- Elements same type
	- Fast iteration
		- Good for math, data processing
	- Efficient multidimensional data

Arrays:
```python
from array import array
a = array("l", [1, 2, 3])

print(type(a))
print(a[0])
``` 
- Numpy arrays: - Container format for passing arrays between libraries - Can be reshaped with shape() function
	- When added together, actually adds instead of concatenating
```python
import numpy as np

v1 = np.array([
	[1, 2, 3],
	[4, 5, 6]
])

print(v1)
print("v1 Python type:", type(v1))
print("NumPy array type:", v1.dtype)
```

- Get the sum of `n` number of dice rolls:
	- Hint: generate 20 random ints between a lower and upper bound

- Pandas:
	- For data analysis and visualization
	- Data types:
		- Series: 1d arrays of any data type 
		- DataFrame: 2d labelled array of any data type