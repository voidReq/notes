- Union:
	- Takes two nodes, and finds their roots
		- If diff trees, makes the root of one the other one's parent
	```python
	union(node1, node2):
		root1 = find(node1) 
		root2 = find(node2)
		if root1 != root2:
			if root1.rank > root2.rank: # the rank is the height
				root2.parent = root1
			else:
				root1.parent = root2
				if root1.rank == root2.rank: # in case they came to be the same rank
				root2.rank++
	```
- Priority queue: a list storing things in an order
	- Uses comparable protocol, not most recently added
- Spanning tree
	- Can get from any node to any other node
- Kruskal's
	- Create a forest, where each vertex is a tree
	- Create sorted set S containing all edges in graph
		- Priority Queue
	- While S nonempty, f not spanning
		- Pop smallest into spanning tree, unless causes cycle
		- Use Unionfind to see if they're one tree, and if connected
	- Just because each node has an edge doesn't mean it's done
- Unionfind has directed edges, but MST are weighted and undirected