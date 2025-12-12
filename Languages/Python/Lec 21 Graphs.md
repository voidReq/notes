```python
T = TypeVar("T")
class TreeNode(Generic[T]):
	def __init__(self, data: T) -> None:
		self.data = data
		self.left: Optional[TreeNode[T]] = None
		self.right = None
	
class BinaryTree(Generic[T]):
	def __init__(self) -> None:
		self.root: Optional[TreeNode[T]] = None
```

- Recursive backtracking
	- for each child in a given node
		- choose a child to explore
		- do all this recursively
		- unselect that child
- Graphs, not trees:
	- No roots/leaves
	- Directed & undirected graphs
		- Directed: Blob is friends with Glob, but Glob not with Blob
		- Undirected: They must be friends with eachother to be friends at all
- Union find:
	- Finds disjoint sets, and represents
	- Each item is a node in a graph
- To find root:
	- Make a method to check if current node is its own parent. If not, return the method recursively with the parameter being the parent node.
- Union:
	- Combines sets containing two nodes into a single set