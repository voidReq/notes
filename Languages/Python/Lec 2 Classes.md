Read from file:
```python
with open('story.txt', 'r', encoding="utf-8") as file:
	for line in file.readlines():
		print(line)
```

When importing a python file, ALL CODE INSIDE IT is run. That's why we use the if name = main thing is run, so we only run main

# Classes
- Encapsulate data and achieve abstraction
- Built ins:
	- str, list 
- Must contain docstring
- METHODS must use self as a parameter, and use self.COMPONENT, because that makes them object-specific 
```python
class Name:
def ___init___(self, param_1: str, param_2: str): # Constructor
	self.our_param_1: str = param_1
	self.our_param_2: str = param_2
def ret_param_1(self) -> str:
	return self.our_param_2
```