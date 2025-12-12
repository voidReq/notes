- Interfaces using abstract classes are enforced
	- Early error catching
- Contracts are followed by convention, but not enforced
	- Specifies what methods should do, rather than list the methods to be implemented
- Len protocol:
	- `__len__()` can be overridden, to replace `len(obj)`
	- Can implement Sized interface, to force sizing
		- `from collections.abc import Sized`
		- `class ClassName(Sized)` -> must implement `__len__()`
- Membership test protocol
	- `in` calls `__contains__()`
	- `from collections.abc import Container`
	- `class Document(Container[str])` -> must implement `__contains__`
- Iterable protocol
	- `for, in` calls `__iter__(self) -> Iterator[str]`  method
	- `__next__(self) -> T`: returns the next value in the sequence, or raises `StopIteration` if there are no more values left to iterate through
	
	```python
	class AlternatingDayIterator(Iterator[str]):
		def __init__(self, days: list[str]) -> None:
			self.index = 0
			
		def __next__(self) -> str:
			#if there are no days left, raise StopIteration
			if self.index >= len(self.days):
				raise StopIteration
			# if there are days left:
				# figure out which day to return next
				# increment index
				# return the day
			day_to_ret = self.days[self.index]
			self.index += 2
			return day_to_ret
	```

```python
class Interable(Iterable[int]):
	def __init__(self, number: int) -> None:
		self.number = number
		
	def __iter__(self) -> Iterator[int]:
		return Digiterator(self.number)
		
class Digiterator(Iterator[int]):
	def __init__(self, number: int) -> None:
		self.number = number
	
	def __next__(self) -> int:
		digit = self.num % 10 # rightmost
		rest = self.number // 10 # integer division (truncates)
		return digit
		
for digit in INTerable(34567):
print(f"{34567}")
```