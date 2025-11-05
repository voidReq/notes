```python
from typing import Callable

def run_mult_times(func: Callable[[], None], times: int) -> None:
	for _ in range(times):
		func()
		
print(run_multiple_times.__name__) #run_multiple_times


def print_name() -> None:
	print('Rasika')
	
run_mult_times(print_name, 5)



def add_two_ints(a: int, b: int) -> int:
	return a + b
	
add_two_floats: Callable[[float, float], float] = lambda a, b: a + b
```
```python
def get_subset_containing_char():
	to_return = pd.DataFrame({
		'Person': [],
		'Age': []
	})
	
	for _, row in df.itterrows():
		if char in row['Person']
			pd.concat(to_return, pd.DataFrame(row), ignore_index=True)
	return to_return
		
		
		
	#or:
	
	return df[df['Person'].str.contains(char)]
	
print(df[df['age'] > 5])
print(df[[True, True, False])
```