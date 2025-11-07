& AND
| OR
^ XOR (exclusive or)
<< left shift
">>" right shift

```C
int x = 6; // 00000110
int y = 12; // 00001100
int z = 0; // 00000000


z = x & y; // 00000100 AKA 4
// Assigns 1 when BOTH positions are 1

z = x | y; //00001110
// Assigns 1 when EITHER of the positions is 1

z = x ^ y; //00001010
// Assigns 1 when ONLY ONE of the positions is 1

z = x << 1; //00001100 AKA 12
//Shifts left by 1

z = x >> 1; //00000011 AKA 24
//Shifts left by 1

```