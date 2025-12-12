- Root node is the start of a tree
- Nodes may contain data
	- Can point to any number of child nodes
- No cycling permitted
- Leaf nodes: nodes with no children
- Multiple nodes should not point to the same child node
- TREE:
```python
from typing import Optional, TypeVar, Generic

T = TypeVar('T')

class Node(Generic[T]):
	def __init__(self, data: T) -> None:
		self.data = data
		self.children: list[TreeNode[T]] = []
	
class Tree(Generic[T]):
	def __init__(self) -> None:
		self.root: Optional[TreeNode[T]] = None
		
	def __str__(self) -> str:
		return _str_recursive_helper(self.root)
	
	def _str_recursive_helper(self, curr_node: TreeNode[T]) -> str:
		# base case
		if self.root is None:
			return "*"
		# recursive
		

entry_way = Node("Entry way")
building: Tree[str] = Tree()
building.root = entry_way

living_room = Node("Living room")
entry_way.children.append(living_room)

```