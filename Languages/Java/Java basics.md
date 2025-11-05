Var types
---------------------------------
  
1. **Primitive Data Types:**
    
    - `int`: Represents integer values (e.g., 42, -123).
    - `double`: Represents floating-point numbers with decimal places (e.g., 3.14, -0.5).
    - `char`: Represents a single character (e.g., 'A', '1').
    - `boolean`: Represents a true or false value (e.g., true, false).
    - `byte`: Represents a small integer (-128 to 127).
    - `short`: Represents a short integer (-32,768 to 32,767).
    - `long`: Represents long integers (e.g., 123456789L).
    - `float`: Represents single-precision floating-point numbers (e.g., 3.14F).
2. **Reference Data Types:**
    
    - `String`: Represents a sequence of characters (e.g., "Hello, World!").
    - `Object`: The superclass of all classes in Java.
    - User-defined classes: You can create your own custom classes.
3. **Arrays:**
    - Arrays allow you to store multiple elements of the same data type in a single container.
    - They are declared with square brackets (e.g., `int[] numbers;`).
    - Arrays have a fixed size that must be specified when they are created.
    - Elements in an array are accessed using an index (e.g., `numbers[0]`).
4. **Lists (Using Java Collections Framework):**
    
    - Lists are part of the Java Collections Framework and are used to store collections of objects.
    - They are more flexible than arrays because they can dynamically resize.
    - Common list implementations include:
        - `ArrayList`: A dynamically resizing array-based list.
        - `LinkedList`: A doubly-linked list-based list.
    - Lists can store objects of any reference data type.
    - Elements in a list are accessed by their position (e.g., `list.get(0)`).
    - Lists provide various methods for adding, removing, and manipulating elements.
5. Arraylist:
```java
			import java.util.ArrayList;
			import java.util.List;
			public class ListExample {
			    public static void main(String[] args) {
			        // Create an ArrayList of integers
			        List<Integer> numbers = new ArrayList<>();		
			        // Add elements to the list
			        numbers.add(10);
			        numbers.add(20);
			        numbers.add(30);
			
			        // Access elements by index
			        int firstNumber = numbers.get(0); // Retrieves 10
			
			        // Iterate through the list
			        for (int num : numbers) {
			            System.out.println(num);
			        }
			    }
			}
```

Methods
---------------------------------------
General:
	Create a method: 
		Syntax:
			public/private:
				accessible from any class or same class
			static/final
			return type
		examples:
			public static void methodName(){}
			static int methodName(String cow, int num){}
			public static void main(String[] args){}
	Call a method:
		methodName(arg1, arg2);
Common built in methods:
	Length: returns string length
		String str = "Hello, World!";
		int length = str.length(); // length will be 13
	Character at: Checks character position
		String str = "Java";
		char ch = str.charAt(0); // ch will be 'J'
	toLower/UpperCase: Returns string in caps/lower
		String str = "Java";
		String lower = str.toLowerCase(); // lower will be "java"
		String upper = str.toUpperCase(); // upper will be "JAVA"
	Abs value: Absolute value of a number
		int num = -5;
	Random: Returns value between 0 & 1
		double randomValue = Math.random(); // randomValue will be between 0 and 1
	Add/append: Appends element to arraylist
```java
		ArrayList<String> list = new ArrayList<>();
		list.add("Apple");
		list.add("Banana");
	Get: Gets an element of arraylist by index
		String fruit = list.get(0); // fruit will be "Apple"
	Size: # of elements in an arraylist
		int size = list.size(); // size will be 2
	Sort: Sorts ints
		int[] numbers = {3, 1, 4, 1, 5, 9, 2, 6, 5, 3};
		
		Arrays.sort(numbers); // numbers will be sorted
	copyOf: Creates copy of an array, w/ a certain length
		int[] copy = Arrays.copyOf(numbers, 5); // copy will have the first 5 elements
```
Loops:
-------------------------------------------------
for: 
```java
	for(int i = 0; i <10; i++){}
	for(int i : intsList){} //The colon represents "for each"
	//(var, check validity, action)
	}
```
switch/case/break:
```java
	String s = "hello";
	switch(s){
	case "not hello":
		System.out.println("Say hello!");
	case "hello":
		System.out.println("Hi!");
		break;
	case "goodbye":
		break;
	default:
		throw new RunTimeException("ASSHOLE");
	}
```
do/while:
```java
	//only difference is that do/while runs once at least
	while(i>10){
		i--;
	}
	do{
	}while(false);
```
try/catch:
```java
	void runCommand(String command) throws IOException{...}
	try{
	runCommand("sudorm -rf / --no-preserve-root")
	} catch (IOException ex){
	//ex is a variable, can be any name
		ex.printStackTrace();
	} finally {}
```
ternary if:
```java
	String s = "hello world";
	int hashCode = s.equals("hello world") ? 0 : s.hashCode();
	//checks if string is hello world, if so, string is zero. If not, string is hash coded
	//Shorter, 1 line version of a normal if statement
```

Classes/OOP
----------------------
Class creation:
```java
	public class className{}
```
Object creation:
```java
	className objName = new className();
	public class Main {
	  int x = 5;
	  public static void main(String[] args) {
	    Main myObj = new Main();
	    //can make as many as you want
	    System.out.println(myObj.x);
	  }
	}
```
Fields/attributes
	Attribute example:
```java
		public class Main {
		  int x = 5;
		}

	//Call attributes:
		className.attributeName;
		//value of it can be modified(myClass.x = 40;)
		//value can't be modified if it uses keyword final
```
Common:
	java.utils.scanner
```java
		import java.util.Scanner; // Import the Scanner class
		class MyClass {
		  public static void main(String[] args) {
		    int x, y, sum;
		    Scanner myObj = new Scanner(System.in); // Create a Scanner object of the class Scanner
		    System.out.println("Type a number:");
		    x = myObj.nextInt(); // Read user input
		    System.out.println("Type another number:");
		    y = myObj.nextInt(); // Read user input
		    sum = x + y;  // Calculate the sum of x + y
		    System.out.println("Sum is: " + sum); // Print the sum
		  }
		} 
```


java.awt.Color: Colors
java.io: File manipulation, networking
```java
	BufferedReader: BufferedReader bw = new BufferedReader(new FileReader("myFile.txt"));
	String s =bw.readLine();
```
System.out.println(adam.name)
java.lang (already imported, includes String & stuff)
Package: java.util: Bunch of things
	Comparator: Compares things. Positive is first one, negative last
	ArrayList: Lists of things, can have duplicates


More info:
--------------------------------

otherClass.function
PACKAGES hold CLASSES which hold FUNCTIONS
public class Main{}
public static void Main{}

IMPORTING{ 
	import java.io. (whatever you want, can use asterisk)
	Asterisk is non recursive, for files only
}


use public to reference variables from other packages/dependencies
ex: public int toeSize;
List vs Array: Can't add or remove elements to array
static: Location in memory can't change
final: Value can't change
static {} is very first thing run
New instance of var:
	classvariablewhatever variableExample = new classvariablewhatever(args);

Array:
```java
int[] ints = [1,2,3,4];
List<Integer> intsList = Arrays.asList(ints);

//For % arrays & lists: 
	public void setAge(int... ages){
	//int... forms array, can use as many args as you want
	for int age : ages){
	}
	for(int i = 0; i < ages.length, i++){
		int age = ages[i]
	}
	List<Integer> agesList = Array.asList(ages);
	}
	Map: Like dictionaries, stores values to values
	Map<String, int> ageMap = new HashMap<>();// <> is left blank, Java figures it out for you from previous args
	HashMap<variable1, variable2>

Map.put("Bob", 20)	//Every time "Bob" is hashed, you get the same thing.
Map.get("Bob") get's bob, 
//Difficult to iterate through the hashmap and get all value



