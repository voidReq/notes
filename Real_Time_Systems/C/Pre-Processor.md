- Before your code even runs, you can perform a number of functions
```C
#include <file.h>
#ifdef ARGUMENT
//do something if an arg was passed upon compiling (e.g., gcc file.c -DARGUMENT)
#else
//do something if it isn't defined
#endif

//You can also create macros (e.g., __LINE__, __FILE__, etc.)

#define (BACON) 1 // whenever BACON is used in code, it will be 1
#define MAX(x, y) (((x) <= (y)) ? (x) : (y)) // can take params
#define fn(a, b) f((a), 2) // can make default params -> this will call f
```