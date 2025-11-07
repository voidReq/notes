Declare using:
- {dataType} {varName}
Can assign by using "=" followed by a value
"#define" creates a text substitution (no type, just replaces raw txt):
```C
	#include <stdio.h> 
	// Defining macros with constant value 
	#define PI 3.14159265359 
	
	int main() 
	{ 
	
		int radius = 21; 
		int area; 
	
		// Using macros to calculate area of circle 
		area = PI * radius * radius; 
	
		printf("Area of Circle of radius %d: %d", radius, area); 
	
		return 0; 
	}
```

const creates a constant:
- const int Thing = 4;
- //can't be changed
- //naming conventions use capital letters to start const name

| Data Type                  | Size (bytes) | Format Specifier |
| -------------------------- | ------------ | ---------------- |
| ****short****              | 2            | %hd              |
| ****unsigned short****     | 2            | %hu              |
| ****unsigned int****       | 4            | %u               |
| ****int****                | 4            | %d               |
| ****long int****           | 4            | %ld              |
| ****unsigned long int****  | 4            | %lu              |
| ****long long****          | 8            | %lld             |
| ****unsigned long long**** | 8            | %llu             |
| ****signed char****        | 1            | %c               |
| ****unsigned char****      | 1            | %c               |
| **float**                  | 4            | %f               |
| **double**                 | 8            | %lf              |
| **long double**            | 16           | %Lf              |
| **String**                 | custom       | %s               |
Buffer/Strings:
- To create a string, use [] after the name to specify byte amounts
	- `char name[25]`
	- `//"name" only takes up 25 bytes, can't store more`
	- `//Not specifying an amount just lets it have any amt`
Arrays:
- To find Size of array, use sizeof in a weird way
	- `int size sizeof(array)/sizeof(array[0])`
- Collection of elements OF SAME TYPE
	- `{arrayType} {name}[] = {el1, el2, etc}
	- `double prices[] = {5.0, 2.0, 3.0}`
- Note that strings are arrays of chars. 
- For an array of strings, simply use another set of []
	- `char cars[][10] = {"mercedes", "ford"}`
	- `//Note that 10 is the max size of EACH ELEMENT, not total`
	- To change an element by index, use strcpy():
		- `strcpy({array}, "{newVal"})`
