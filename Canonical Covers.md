- Checking every functional dependency hen data is updated is slow/expensive
- Therefore, canonical covers exist: F_c
	- Canonical covers have the same end result, but are shorter and cleaner
	- Notably, there can be multiple canonical covers for the same F
- Canonical covers remove bloat:
	- For instance:
		- If AB->C, but A alone is enough to tell you C, then B is extra
		- If A->BC, but C can already be figured out using other rules in the list, C is extra
- Ex:
Given:
```
A->BC
B->C
A->B
AB->C
```
We can clean it up by doing the following:
```
# Combine
If A->BC and A->B, they can be combined into A->BC

# Check left sides
If A->B and B->C, we can prove C with A, so we can delete AB->C

----------
Currently, we have:
A->BC
B->C
A->B
----------

# Check right sides
As we have A->BC, A->B, and B->C, we can get to C through B already, so we can delete A->BC


----------
FINAL:
A->B
B->C
----------

```
