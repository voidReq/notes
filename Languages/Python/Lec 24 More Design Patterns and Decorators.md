## Design Patterns
- Strategy patterns
	- Allows for altering distance definition at run time
- Maps (Google Maps navigation):
	- Users can choose to prioritize:
		- Shortest path
		- Shortest time
		- Least emissions
		- Least tolls
		- Maximize sightseeing
## Decorators
- Functions are objects
	- Can be put in a list of callables
	- Can print their attributes
```python
	def bacon():
		print("hi")
	print(bacon.__name__)
```
- Function decorators mutate a function to modify what it does
	- `@time_calls` modifies a given fn to print the time it took to run
	- Wrappers will override metadata by default (i.e., `fn.__name__` or `fn.__docs__`)
		- Can use `@wraps` in inside of the function
- Example making a decorator:
```python
def time_calls(func: Callable[..., Any]) -> Callable[..., Any]:
	def wrapper(*args: Any, **kwargs: Any) -> Any:
		now = time.time()
		return_value = func(*args, **kwargs)
		print(f'Executed {func.__name__} with {args} and {kwargs} in {time.time() - now}ms')
		return return_value
	return wrapper
```
- Common usage is in temporal caching/memoization
```python
R = TypeVar("R")

def memoize(func: Callable[..., R]) -> Callable[..., R]:
	cache: dict[tuple[Any, ...], R] = {}
	def wrapper():
		if args in cache:
			return cache[args]
		result - func(*args)
		cache[args] = result
		return result
	return wrapper

@memoize
def fibonachi(x):
	# implementation...	
	pass
	
```
- Class decorators exist in Python, although more popular in other OOPs, like Java
	- Basically works the same
	- Takes a class as an input and returns a class
```python
def class_wrapper():
	original_init = cls__init
	@warps(original_init)
	def new_init():
		printf("Creating instance of our class, cls")
		original_init(self, *args, **kwargs)
	
	cls.__init__ = new_init
	return cls
```