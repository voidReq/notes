```python
def map(original: List[T], converter: Callable[[T], [R]])
	return [converter(item) for item in original_list]
```
is the same as 

```python
def map(original_list: List[T], converter: Callable[[T], [R]]) -> List[R]:
	to_ret: List[R] = []
	for item in original_list:
		converted_item: R = converter(item)
		to_return.append(converted_item)
	return to_return
```


```python
def get_num_pages(book: Book) -> int:
	return len(book.content)
	
summer_reading_list = [Book('1984', 'Orwell', ['page1' ,'page2'])]

print(map(summer_reading_list, get_num_pages))
```


- split(): split a str into separate words
	- Space by default, but can use a sep
		- `words =: List[str[ = lyric.split(serp = e)]]`
- 