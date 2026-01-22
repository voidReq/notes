- Denoted with an arrow (A->B means for a given A, each B has the same value)
- Functional dependencies refer to when two attributes are always together
	- For instance, say we have a relation for professors
	- Within this relation, both the department name and department budget are listed
	- The two act as a functional dependency because the department name is always paired (or should always pair) with the same department budget
	- Note that the reverse is not necessarily true (budget->name)
- Utilized to:
	- Test instances of relations to see if they satisfy a set of functional dependencies
	- Specify constraints on the set of legal relations
- Trivial dependencies:
	- Always true, no matter what data is placed in the table
	- Ex: (Name, Age) -> Name
		- If you know the name and the age, you know the name
- Note this following example:
	- You may have a list of classrooms, where each room number has a different capacity
		- Room_num -> Capacity seems to work
	- However, two different buildings could have the same room number with different sizes
		- Therefore, it must become (Building, Room_num) -> Capacity
- The operator is the same as the conditional operator in math for a reason
- If you know A->B, and B->C, by transivity you can conclude A->C
- Closure (F+)
	- Master list: set of every functional dependency you could figure out, both through base rules and applying logic
	- Ex: Given A->B, B->C, find the closure
```
{A->B, B->C}
{A->C}
{A->A, B->B, C->C, AB->A, BC->B, BC->C, etc.}
{AD->BD, AC->BC, etc.}
```

- Enforcing lossless decomposition
	- Proper use of primary keys
	- Use of foreign keys


### Armstrong's axioms + more:
- Used to determine F+, the closure of a set of functional dependencies (F)
- Reflexivity:
	- If a is a set of attributes and b subsets a, then a->b
- Augmentation:
	- If a->b and y is a set of attributes, then ya->yb
- Transivity:
	- if a->b and b->y, a->y
- Union:
	- If a->b and a->y, a->by
- Decomposition:
	- If a->by, then a->b and a->y
- Pseudotransivity:
	- If a->b and yb->S, ay->S
