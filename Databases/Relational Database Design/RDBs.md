### Schemas
- Schema is structure of relatable DBs
	- Ex: dept(<u>name</u>, budget, size)
		- <u>name</u> represents the primary key
### Keys
- Keys in a given relation are not duplicated (are unique)
- Keys are composed in a hierarchy, where each is more specific than the last
	- Superkeys, candidate keys, primary keys
- Superkeys:
	- Most general
	- Can contain extra info that isn't necessarily needed
	- Ex: if we used (<u>name</u>, size) to reference a dept
- Candidate keys:
	- No extra columns
	- Tables can have multiple candidate keys
	- Ex:
		- If a student relation has both Student_ID and SSN, both are unique to the student
		- Both could be used as reference
- Primary keys:
	- One per table
	- Unique
	- Chosen by DB designer as principal means of identifying a record

### Notation
- α typically represents a set of attributes
- When a set of attributes is a superkey, it's denoted by *K*
- Relation names are lowercase
- r(R) refers to a relation r with schema R
	- r, the relation, is the actual data
	- R, the schema, represents the structure
	- Sometimes, when it's clear an instance is being discussed, the relation name can be used (i.e., r) 

