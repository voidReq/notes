- In C, if you care to be consistent with your switch statements, consider using function pointers instead.
- Instead of having a switch where 4 different events can happen, make 4 different functions and a function pointer
```C
void event0(void);
void event1(void);
void event2(void);
void event3(void);

void (*function_array[4])(void);

function_array[0] = &event0;
function_array[1] = &event1;
function_array[2] = &event2;
function_array[3] = &event3;

function_array[2](); // calls event 2 function

int n = 2;

switch(n){
	case 0;
		event0();
	case 1;
		event1();
	case 2;
		event2();
	case 3;
		event3();
}

// can now be performed with:

function_array[n]();

```