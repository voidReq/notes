- Immutable: can't be modified after creation
	- Lists: mutable
		- list.append(val)
		- Can be sorted in place
		- list.sort()
	- Tuples: immutable
		- Can't append/modify
		- Can't be sorted in place
		- The variable my_tuple is a pointer, and thus mutable -> can be reassigned somewhere else
```python
my_tuple: Tuple[int, ...] = tuple([-i for i in range(5)])
my_tuple = tuple(sorted(my_tuple)) # returns a copy of the tuple
```

# Generics
- In this class, elements of the list ought to be same type
	- List type can make objs of diff types as List is a generic type
- To make generics: Create type variable T

```python
from typing import List, TypeVar, Generic
T = TypeVar('T')

class Stack(Generic[T]):
def __init__(self) -> None:
	self.items: List[T] = []
	
def push(self, item: T) -> None:
	self.items.append(item)

def pop(self) -> T:
	return self.items.pop()
	
def is_empty(self) -> bool:
	return not self.items
	
my_stack: Stack[int] = Stack()
my_stack.push(4)
print(my_stack) # 4
my_other_stack: Stack[str] = Stack()
	
```


- Generic type: class w/ type variable:` List[T]`
- Parameterized: generic w/ type variables filled in:` List[str]`

```python
class Thing([Generic[T]]):
	def __init__(self, item: Optional[T])
	
string: Thing[Thing[str]] = Thing(Thing['hi']) # valid
```

- Map(): converts a list of one type to list of another, should use generic type T

```python

T = TypeVar('T')
R = TypeVar('R')

def map(original_list: List[T], converter: Callable[[T], [R]]) -> List[R]:
	to_ret: List[R] = []
	for item in original_list:
		converted_item: R = converter(item)
		to_return.append(converted_item)
	return to_return

names_List[str] = ['rasika', 'mini']

def get_num_chars(word: str) -> int:
	return len(word)
	
name_lengths: List[int] = map(names, get_num_chars)
print(name_lengths)
```

- Can name which arg is which as we pass them in, if there are a lot and we want them organized