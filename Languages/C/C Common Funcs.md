### INPUT
- getchar() collects user input, reading a single character:
```C
#include <stdio.h>

// Driver code
int main()
{
	int character;
	character = getchar();

	printf("The entered character is : %c", character);
	return 0;
}
```
- putchar() prints the single character:
```C
#include <stdio.h>

// Driver code
int main()
{
	int character;
	printf("Enter any random character between a-z: ");
	character = getchar();

	printf("The entered character is : ");
	putchar(character);
	return 0;
}
```
- scanf() collects user input, type can be specified:
```C
scanf("{varType}", &{varNameToStore})
//& represents the address of the variable
//varType should be replaced by representatives (e.g., %d)
//ONLY READS UP TO WHITESPACES
```
- fgets() collects user input, PAST whitespaces:
```C
fgets({varNameToStore}, {byteSize}, stdin})
```

### STRINGS
- strcmp() compares contents of strings:
	- `strngcpm({string1},{string2})`
- strlen() gets length of string:
	- `strlen({string})`
- sizeof() returns bite size of a var:
	- `sizeof({var})`
- strcat() adds a second string into the first passed:
	- `strcat({str1}, {str2})`
- strcpy() copies contents of first passed into second passed:
	- `strcpy({str1}, {str2})1

