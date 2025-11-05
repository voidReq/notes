- Accumulator pattern: Combining an amount of things into something
- Exercise
	- Ask user how many numbers they want to input
	- Asks for that many numbers
	- Prints min, max, and avg
	- No lists allowed
```python
from typing import Optional
def print_min_max_avg() -> None:
	min_so_far: Optional[float] = None
	while True:
		try:
			count = int("How many nums?")
			break
		except ValueError:
			print("Bad boy.")
	for _ in range(count):
		number = float(input("Enter your number!"))
		sum += number
		if min_so_far is None or number < min_so_far:
			min_so_far = number
```

- Sets
	- Unordered
	- No repeated items
	- Operations:
		- Union: `a | b`
		- Union: `a & b`
		- 
	- Find number of unique words in a given string:
	```python
	from typing import Set
	def get_num_unique_words(sentence: str) -> int:
		return len(set(sentence.split()))
	```
	
	```python
	def check_for_equal_bdays(self) -> None
		birthdays: set[tuple[int, int]] = set()
		for _ in range(40):
			month = int(input("Month"))
			day = int(input("Day"))
			bday = (month, day)
			if birthday in birthdays
				return True
			birthdays.add(Birthday)
		return False
	```

```python
type({'hey'}) # set
type({}) # dict
type({'hi':'there'}) # dict
```

```python
def get_word_counts(text: str) -> dict[str, int]:
	# how many times words appear
	word_counts: dict[str, int] = {}
	for word in text.split():
		#previous_count = word_counts.get(word, 0)
		word_counts[word] = wird_counts.get(word, 0) + 1
	return word_counts
```