See [[Register Cheat Sheet]]

- Intel syntax:
	- Disclaimer: the correct registers are not used here. I'm using RAX and RBX interchangeably, which is not good convention. That being said, I'm tired.
- 
```
INSTRUCTION destination, source
MOV RAX, 5    ; Immediately 
MOV RAX, RBX    ; Copy RBX value to RAX
```
- Square brackets `[]` get addresses
	- `[0x2000]`: Value at address 0x2000
```
MOV RAX, [RBX]    ; Memory at address in RBX to RAX
MOV [RAX], RBX    ; Value in RBX to address in RAX
MOV RAX, [0x1000]    ; RAX = value at address 0x1000
MOV [0x2000], RAX    ; RAX is stored at address 0x2000
MOV [RAX], [RBX]    ; INVALID--can't move memory directly to memory
MOV [RAX], 100    ; INVALID--Can't move immediate to memory w/ out size
MOV BYTE [RAX], 100    ; Works
MOV AL, 0xFF    ; Move byte
MOV AX, 0xFFFF    ; Move word
MOV EAX, 0xFFFFFFFF    ; Move dword
MOV RAX, 0xFFFFFFFFFFFFFFFF    ; Move qword
```