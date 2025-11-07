 - Boolean storage can be optimized with bitwise operators
	 - Storing booleans inside of one char will take 8 bytes for 8 booleans
	 - 8 separate booleans would take 64 bytes
 ```C
 #define FLAG_1 (1 << 0) // 00000001 -> 00000001
 #define FLAG_2 (1 << 1) // 00000001 -> 00000010
 #define FLAG_3 (1 << 2) // 00000001 -> 00000100
 #define FLAG_4 (1 << 3) // etc.
 
 unsigned char flags = 1; // stored as: 00000001
						  // only flag 1 is currently on
 
 if (flags & FLAG_1){ // will only pass if FLAG_1 is on, which it currently is
	 printf("FLAG_1 is ON!")
 }
 
flags |= FLAG_1;        // turn on FLAG_1
flags &= ~FLAG_2;       // turn off FLAG_2
flags ^= FLAG_3;        // toggle FLAG_3
 ```
- Alternatively, we can use bit-fields, where we can specify how many bits are taken up by a bool
```C
typedef struct {
	bool flag_1 : 1; // takes up 1 bit
	bool flag_2 : 1; // takes up 1 bit
	bool flag_3 : 1;
	bool flag_4 : 1;
	bool flag_5 : 2; // takes up 2 bits ()
} flags_t;

flags_t flags;
flags.flag_1 = 1;
flags.flag_2 = 1;
flags.flag_3 = 0;
//flags.flag_4 = 2; // do not do this.
flags.flag_5 = 2; // that's fine
```