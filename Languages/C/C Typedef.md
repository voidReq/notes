Gives a datatype a "nickname"

The following:
```C
char user1[25] = "hi";
char user2[25] = "yo";
char user3[25] = "wsg";
```
Can be changed to:
```C
typedef char user[25];
user user1 = "hi";
user user2 = "yo";
user user3 = "wsg";
```

Can also be used with a struct
```C
typedef struct{
char name[25];
} bacon;

bacon hello = {"hello"};
strcpy(hello.name, "Good evenin!");
```

