```python
class Shape(ABC):
	@abstractmethod
	def get_area(self) -> float:
		pass
	def get_permiter(self) -> float:
		pass
		
shape = Shape()
#errors, because this class is abstract

class Rectangle(Shape):
	def __init__(self, ln, wd):
		pass
	def get_area(self) -> float:
		return ln * wd
	def get_perimiter(self):
		ret 2*ln + 2*wd
rect = Rectangle(2, 4) # works
```
- in interfaces, subclasses must implement EVERY method