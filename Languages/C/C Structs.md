- Collection of related vars, of varying types
- In one name in one block of memory
- Classes, but without methods

- `struct Name{}`
- Capitalize name

```C
struct Player{
	char name[12];
	int score;
}

//Access using {structName}.{memberName}
struct Player player1;
struct Player player2;

strcpy(player1.name, "Joe");
player1.score = 4;

strcpy(player2.name, "Bill");
player1.score = 3;

```

- To make an array of structs
```C
struct Student{
char name[12];
float gpa;
};

struct Student student1 = {"Spongebob", 3.0};
struct Student student2 = {"Joe", 2.4};
struct Student student3 = {"Idk", 5.3};
struct Student student4 = {"Bacon", 143.2};

struct Student students[] = {student1, student2, student3, student4};

for(int i = 0; i < sizeof(students)/sizeof(students[0]); i++){
printf("%s\n", students[i].name)
}
```