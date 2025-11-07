- Write to a file:
```C
FILE *pF = fopen("test.txt", "w"); //Pointer to a file
// Use "a" to append
//You can also add a file path, but USE "\\" not "\"

fprintf(pF, "Thing to add to file"); //Overwrites anything
fclose(pF);
```
- Delete a file:
```C
if(remove("test.txt) == 0){
	printf("Success!");
}
else{
printf("Failure");
}
```
- Read a file:
```C
FILE *pF = fopen("poem.txt", "r");
char buffer[255]; Holds 1 line at a time, max 255 bytes


while(fgets(buffer, 255, pF) != NULL){ // Puts a line into "buffer"
	printf("%s", buffer);
}

fclose(pF);

```