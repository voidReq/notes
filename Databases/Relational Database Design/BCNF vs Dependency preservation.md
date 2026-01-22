 - Boyd-Codd Normal Form (BCNF) is a DB design seeking to eliminate redundancy
- Everything in a table must be a fact about the key
- A table is in BCNF if, for every functional dependency, at least one of the two is true:
	- The rule is trivial (A->A, or something else obvious)
	- A is a superkey (so A can uniquely identify everything in that table)
- If a table isn't BCNF, you split it into smaller ones
- DBs are in tug-of-war between ensuring no repeated data and trying to make the rules easy to check
- Dependency preservation
	- When DBs are updated, they must check if functional dependencies are followed
	- Efficient (involves columns in the same table):
		- Looks at only that table
	- Costly (columns split into different tables)
		- DB has to join the tables to check
	- When designs split a rule across tables so it can't be checked easily, it's not dependency preserving
- However, proper DCNF means decomposition
- 3NF (compromise)
	- When perfect BCNF is impractical, 3NF is used (relaxed BCNF)
	- Every rule in a table must meet one of the three for it to be in 3NF
		- Trivial
		- A is a superkey (can contain extra info)
		- B is part of a candidate key (there can be multiple candidate keys)
	- You can always get a 3NF design that's both lossless and dependency preserving
- Tradeoffs
	- In an ideal world, you want all three:
		- BCNF
		- Losslessness
		- Dependency preservation
	- However, this isn't always achievable, so you often must choose between the two
		- BCNF (cleaner data)
		- 3NF (easier rule checking)
- Multivalued attributed
	- Even if a table is BCNF, might still have redundant data
	- Example: a parent has two children, and two phone numbers

| Parent ID | Child | Phone number |
| --------- | ----- | ------------ |
| 999       | A     | 111-2222     |
| 999       | A     | 222-1111     |
| 999       | B     | 111-2222     |
| 999       | B     | 222-1111     |
