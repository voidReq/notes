# Gen memory
- Memory: Array of bytes in RAM
- Memory block: A unit that holds the value
- Memory address: Address of where the memory block is
```C
char a = 'x'; 
// 1 byte
// a stores the VALUE
// &a is the address

printf("%p", &a); //print the address

Note that [] MULTIPLIES the default amount of bytes
For instance, a short usually takes 2 bytes 
short b[3]; //This NOW takes 6 bytes
```

# Pointers :(
- Holds the ADDRESS of a variable
- Why this heinous thing is used:
	- Less execution time
	- Modify original variable
	- Can form data structures
	- Return multiple values from a function
	- Search/sort data sets easily
	- Dynamic memory allocation

- `*` is the indirection operator, the value at an address
```C
	int x, y;
	int *px;
	px = &x;
	y = *px;
	//is equivalent to
	y=x;
```

- Make sure data type of pointer is consistent with type of variable!
```C
	int age = 21;
	printf("Address: %p", &age); //Prints the address
	printf("Value: %d", age); //24
	
	//We can store the address in a pointer, like so
	
	int *pAge = &age; //Putting "p" after "*" is just a convention
	//Creates a pointer named pAge, 
	//that stores the memory address of an int named &age
	
	printf("Value of pAge: %p, pAge); //Prints the address
	printf("Value at pAge address: %d:", *pAge); //24
```

```C
	void printAge(int *age){
		printf("You are %d years old\n", *pAge); //21
	}
	int main(){
		int age = 21;
		int *pAge = &age;
		
		printAge(pAge)
	}
```

- If you are declaring a pointer but NOT assigning a value yet, assign to NULL
```C
int age = 21;
int *pAge = NULL;
pAge = &age;
```

- When you're directing to the first element of an array:
```C
	//Where pa is a ptr and a is an array
	pa = &a[0];
	//is also
	pa = a
	//Note that array names are CONSTANTS, not variables.
	//You CAN't do a=pa, or p=&a
```

- Arrays/Pointers:
	- You can pass parts of arrays into functions, using a pointer
	- If a is an array, `f(&a[2])` and f(a+2) both pass `a[2]`, as they're both pointer expressions
	- Example of finding length of string: (pointers = arrays!)
	- Looking back, I don't know what's going on in this example
```C
int strlen(s);
char *s;
{
int n;
for (n = 0; *s != '\0'; s++) n++;
	return n;
}
/*
You can increment s as it's a pointer variable
s++ increases strlen's private copy of the character string address
As parameters in a function definition, 'char s[];' and 'char *s' are the same
*/
```

# Dynamic Memory Allocation
- By default, program values are stored in RAM
- Memory is allocated into stacks and heaps
	- Memory is just an ordered list of addresses containing vars
- The stack is where regular vars are stored
	- Data is stacked, ordered, next to existing memory allocated for defined vars![[C stack.png]]
	- The stack is ordered, all data has fixed size (floats 4 bytes, etc.)
	- When a function is called, it's local variables are placed on the stack
		- When it returns, they're removed
- The heap is for dynamic memory allocation
	- Blocks of memory on the heap can be requested as the program executes
	- Given block of memory, and pointers will point to this block
	- Heap data can be different sizes, not necessarily in order
- Malloc can request blocks of memory
	- malloc(byteNum) allocates some amount of space onto the heap
	- Returns typless ptr to this block of memory
	- sizeof(type) can get size of a type, to help with calculations
![[C Memory Diagram.png]]
```C
int *a = malloc(sizeof(int)*10);
//Called a dynamically allocated array, can access as an array
//Returns a pointer to memory block, 40 bytes (for 10 integers)

for int i = 0; i < 10; i++) a[i] = 10 - i; 
//Reverses vals (a[0] = 10, a[1] = 9, a[5] = 5)

free(a); //Clears the memory block at address "a"
```
- Memory Locations on the stack are freed up when a function returns (local variables no longer exist)
- If we keep calling functions with local vars, we add more and more to the stack (Memory leak)
```C
int main(){
	while (1) memory_hog(128000);
	return 0;
}

void memory_hog(int size){
	int *a = malloc(size);
}

/*
Heap will grow until there's none left
*/
```
- calloc works the same as malloc, but zeros the space out.
```C
int *a = calloc(10, sizeof(int));

for int i = 0; i < 10; i++) a[i] = 10 - i; 

int *save = a;
free(a); 

/*
Clears the memory block at address "a"
The populated data is NOT CLEARED, the memory block is just made accessible again
If you print out what's at "save", all the data remains
*/
//Calloc will clear this space
```
- realloc lets you resize space:
```C
int *a = calloc(40);
a = realloc(a, sizeof(int) * 15); //Adds 60 bytes to a
free(a);	
```

