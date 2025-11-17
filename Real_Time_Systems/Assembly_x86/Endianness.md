- Little-Endian
	- Used by x86/x86-64
	- Least significant byte is stored at the lower address
```
Value 0x12345678, stored at 0x1000
0x1000: 0x78
0x1001: 0x56
0x1002: 0x34
0x1003: 0x12
```
- Big-Endian
	- Used by some network protocols & various architectures
	- Reverse of the above (Most significant at lowest address)
	- `htonl()` - Host TO Network Long (convert to big-endian)
	- `ntohl()` - Network TO Host Long (convert to little-endian on x86)