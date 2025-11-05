- You can't add custom classes to sets if they aren't hashable
- `__hash__(self) -> int`: `from collections.abc import Hashable`
- hash:
	- Map a val to an int index
- Hash table:
	- List storing elements via hashing
- Hash set:
	- Set of elements stored using hash function
- Hash function:
	- Algorithm mapping values to indexes
### Example:
hash function:
`i % length`
```python
set.add(11) # 11 % 10 == 1
set.add(49) # 49 % 10 == 9
set.add(24) # 24 % 10 == 4
set.add(7) # 7 % 10 == 7
set.add(17) # 7 % 10 == 7 -> makes a hash collision
```
- Avoidance of hash collisions:
	- Probing:
		- Moving the issue child into the next available index
	- Chaining
		- Putting a list at each index, and that list will be searched through
- Hash rules:
	- Must always return same val given the same object