### Business Requirements (PDF)
- Business domain language
- Narratives
- Rules (bullet points)
- Highlighted nouns/verbs

**Example**
- Rules:
	- Multiple **students** in the **class**
	- Each **student** has multiple **grades**
	- Some **grades assigned**, some not
	- A **grade** range 0-100
	- Only care about current **class**
- Nouns: Class, Student, Grade
- Verbs: Has, assigned
- Attributes: class, student

### Conceptual Model (UML)
- Class diagram from UML
	- Used for conceptual model
- Attributes can have multiple values
- In class diagrams, methods don't matter, foreign keys don't matter
	- Have attributes and attribute types (business specific)
- Cardinality:
	- `1`: 1 relation
	- `1..*`:  Between 1 and any number of relations
	- `*`:  Any number of relations
	- `1`: May or may not have 1 relation
- Name your relations, include direction and cardinality
	- Given "Team" and "Player" tables:
	- `Team` <- plays, 0..* `Player`
- Can have aggregations, compositions, generalizations

### Logical Model
- Relational: ERD (crow's foot)
- Start from conceptual model
- Choose database type
	- Solve multiple value attributes
	- Solve many-to-many relationships
	- Identify foreign keys
- Can't have generalizations, compositions, aggregations

### Physical Level
- Relational: SQL DDL
- Have the relation schema
- Make the actual code

# GENERAL PROCEDURES