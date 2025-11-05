- Python doesn't block visibility at all
	- Reliant on unenforced guidelines
	- vars beginning w/ _ can be accessed, but it's discouraged
	- vars beginning w/ __ can ONLY be accessed by doing `_className__varName`
- Something marked with the @property vector:
	- An attribute that's re-calculated each time it's accessed
	- Marks a method
	- If you create an "attribute" using the @property method, you can make a setter using @age.setter
```python
class Person
	def __init__(self, first_name, last_name):
		self._first_name = first_name
		self._last_name = last_name
		self._age = age
	
	@property
	def name(self)
		return f'{self._first_name} + {self._last_name}
	@property
	def age(self):
		return self._age
		
	@age.setter
	def age(self, new_age)
		self._age = new_age
		
mini: Person = Person("mini", "bacon")
print(mini.name)

```