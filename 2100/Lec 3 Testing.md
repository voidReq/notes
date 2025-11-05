- Create a test class for every single class.
- For each test, make a test method with a comprehensive name
- Test:
	- Normal case
	- Edge cases
	- Each branch of conditionals
	- Make sure errors are raised
- unittest
	- setUp(): Runs before each test
	- tearDown(): Runs after each test
	- Classes: MUST USE DECORATOR:
		- setUpClass(cls) -> None: Runs once before any tests
		- def tearDownClass(cls) -> None: Runs after each tests
- Try/Except
	- Only use when necessary, alternative to self.assertRaises()

```python
import unittest


class Cat:
	def __init__(self, name:str):
	def makeSound(self):
	def rename():
		if(name ==''):
			self.name = "tootsie"
			raise ValueError("NOOOOO")
		
	
	

class TestCat(unittest.TestCase):
	def test_two_year_old_meow(self) -> None:
	#to be run, fn  must start with test_
		self.tootsie.birthday()
		self.tootsie.birthday()
		self.assertEqual(tootsie.makeSound(), "meow meow ")
		# Can raise ValueError
	def test_rename_empty_str(self) -> None
		with self.assertRaises(ValueEror):
			blank = Cat('')
	def setUp(self) -> None:
		self.tootsie = Cat('Tootsie')
def main() -> None:
	unittest.main()
	
if __name__ == __main__:
	main()
	
```

