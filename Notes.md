# Java Syntax
	
pvsm: `public static void main{};`

sout: `System.out.printLn();` note: uses CRLF line spacing
	
## Strings:
Compare Strings: `variable.equals("txt");`

Use `var.length()` method to get int with length

Use `var.substring(i, j)` to extract the String starting at index i and going up to but not including index j

Use `Integer.toString(n)` to turn an integer into a String

Use `.toLowerCase()` OR `.toUpperCase()` to turn Strings into all lower or upper case.

To replace a part of a String, `.replaceAll("x", "")` can be used on String variables.

## Printing Formated Numbers to Console:
`System.out.printf("%.2f", val);`
			
`System.out.format("text %f.", val);`

Flags:

* o : octal integer
* e : floating-point in scientific notation
* d : decimal integer [byte, short, int, long]
* f : floating-point number [float, double]
* c : character Capital C will uppercase the letter
* s : String Capital S will uppercase all the letters in the string
* h : hashcode A hashcode is like an address. This is useful for printing a reference
* n : newline Platform specific newline character- use %n instead of \n for greater compatibility

* `-`: left-justify ( default is to right-justify )
* `+` : output a plus ( + ) or minus ( - ) sign for a numerical value
* `0` : forces numerical values to be zero-padded ( default is blank padding )
* `,` : comma grouping separator (for numbers > 1000)
* ` ` : space will display a minus sign if the number is negative or a space if it is positive
	
## Scanner:

	Scanner myScanner = new Scanner(System.in);
	String width = myScanner.nextLine();

*Note:* `System.in` indicates that the *Scanner* is going to read nextLine inputted by the user using keyboard.

Scanner can also take in integers, floats, doubles...
	
	float width = Float.parseFloat(myScanner.nextLine());
	int width = Integer.parseInt(myScanner.nextLine());

## Random Generator:	
	
	Random myRandom = new Random();
	int randNum = myRandom.nextInt(#); 
	
Where # is the number of elements inside an array of integers [0:(#-1)] 
	
## Arrays:	
First method:

	int[] arr = new int[3]; //initializing; 
	arr[0] = 15; //Assigning
	
Second method:

	int[] arr = {15, 25, 35};
	
## Conditionals:
If Statements: 
	
	if (){
	} else if () {
	} else {
	}
	
Switch Statements:

	switch (variable){
		case "compared to condition 1":
			statement;
			break;
		case "compared to condition 2":
			statement;
			break;
		default;
			statement;
			break;
	}
	
## Loops:
		
`while (condition) { //Statement }`

`do { //Statement } while (condition);`

`for (initialization, termination; increment){//Statement} >>> for (int i=;i<4;i++){//Statement}`
		
Enhanced for loop (deals with arrays):
		
`for (int element : arrayName){} //Doesn't affect the original array`

# Classes

A class is the blueprint used to instantiate an **Object**. It contains **properties, methods, getters & setters**, and **constructors.** 
		
## Properties:
Note: properties should be private: **Encapsulation**

## Methods:
Methods are blocks of code that can be called when needed. 

When we run a Java program the main method is called by default.

Syntax: 

	<Access Modifier><static Or not><ReturnType><methodName>(ParameterType, par){ ...Method body...	}
	
Most common example is the main method: `public static void main(String[] args) { ... }` 	

### constructors:

Constructors are used to create an instance of a class, or in other words an object.

	public ClassName(dataType var, ....){
		this.var = var;
	}
	
To create a new object we use: `Class nameOfObject = new Class(parameters);`

Note: if we don't write a constructor for a class, the compiler will provide a default one to be used.

### Getters:

Used to get values of properties inside an object.

	public returnType getVar(){
		return this.var = var;
	}

Note: in IntelliJ we can just type getVar to automatically generate a getter.

Note: for boolean type we use isVar instead of getVar.

### Setters:

Used to set values of properties inside an object.

	public void setVar(dataType var){
		this.var = var;
	}

Note: in IntelliJ we can just type setVar to automatically generate a setter.

Note: use **alt + insert** to quickly generate.

Note: Getters, setters, and methods need to be public in order for us to be able to manipulate the object. Otherwise, if we need only the direct child to be able to use the parent class's properties and methods we can set them to `protected`.

Note: to create a read-only property we don't create a setter.
			
## Interfaces, Composition, and Inheritance

An **interface** is a contract that holds all the methods (minimum requirements) that need to be implemented by the class. 

To implement interfaces use `implements Interface1, Interface2 ` next to the Class name.

We can extend Class **to inhert all there properties and mehtods**. To extend a parent class use `extends ParentClass`.

By default, all classes extends the *Object* class.

`super(parameters)` is used to inherit parent's constructor:

	public ClassName(String message){
		super(message); 
	}

**Composition** means that we can build any object using other objects as properties.
			
### Abstract Classes:
	
A mixture of an interface and a parent class.
		
	public abstract Class{ 
		//Properties
		
		//Abstract methods: 
		//Doesn't require a body for methods
		public abstract void doSomething();
	}

# Data Structures

Simplified Class Hierarchy of useful Date Structurs:

* Object
  * AbstractCollection<E> (implements Collection<E>)
    * AbstractList<E> (implements List<E>)
      * **ArrayList**<E> (implements List<E>, as well as other interfaces)
      * AbstractSequentialList<E>
        * **LinkedList**<E> (implements List<E>, as well as other interfaces)
    * AbstractSet<E> (implements Set<E>)
      * **HashSet**<E> (implements Set<E>, as well as other interfaces )
        * LinkedHashSet<E> (implements Set<E>,  as well as other interfaces)
  * AbstractMap<K,V> (implements Map<K,V>)
    * **HashMap**<K,V> (implements Map<K,V>, as well as other interfaces)
      * LinkedHashMap<K,V> (implements Map<K,V>)
	

## List: ArrayLists: https://docs.oracle.com/javase/8/docs/api/java/util/ArrayList.html

Lists only accept elements that are objects [Wrapper Classes], such as Integer, Float, Double, etc... as opposed to primitive types, such as int, double, float, etc. 

To **declare the list** we use: 

`List<Integer> myInt = new ArrayList<Integer>();`

**.size()** used to **get the length.** Example: `nameOfList.size()`

**.add(object)** used to **add objects** to the list. Example: `nameOfList.add(object);`

**.get(int index)** used to **get an element.** Example: `nameOfList.get(index));`

**.indexOf(object)** used to **fetch an index** of a specific object in the list. Example: `int index = myList.indexOf("Sal");`
         
**.remove(object)** used to **remove** an element from the list: `nameOfList.remove("Sal");`

**.clear()** used to **clear** a list: `nameOfList.clear();`

To **display all elements** of a list, we can use any loop as shown below:

        for(String element: nameOfListList){
            System.out.println(element);
        }
        
        for(int i =0; i<nameOfList.size(); i++){
            System.out.println(myList.get(i));
        }
		
### Iterators:

Used to iterate through all elements of a list.

Declared as: 

`Iterator<String> iter = names.iterator();` 

Methods: `.hasNext()` and `.next()`

Then can be used as follows:

        while (iter.hasNext()) {
            System.out.println(iter.next());
        }

### AutoBoxing vs. UnBoxing:

To assign a primitive type to a Wrapper Class, the following would be unnecessary and only used for older versions of Java: `Integer myInteger = new Integer(12);` This is also unnecessary: `myInteger = Integer.valueOf(12);`

Instead, we can use: `Integer myInteger = 12;` This is called Autoboxing.

To do the opposite, we can use: `int myPrimitive = myInteger;` This is called Unboxing.

## List: LinkedLists: https://docs.oracle.com/javase/8/docs/api/java/util/LinkedList.html

A linked list consists of nodes where each node contains a data field and a reference(link) to the next node in the list.

Similar to ArrayLists, but more dynamic and allows for usage of more methods, such as `set`, `getFirst`, and `getLast`

Advantages over arrays:

1. Dynamic size
1. Ease of insertion/deletion

## Set: HashSets: https://docs.oracle.com/javase/8/docs/api/java/util/HashSet.html

Basically, an un-ordered list that doesn't accept duplicate entries.

Instantiating, `Set<Integer> setName = new HashSet<>();`

Adding entries, `setName.add(5);`

*Note:* For more methods, check the link above.

## Map: HashMaps: https://docs.oracle.com/javase/8/docs/api/java/util/HashMap.html

HashMaps are maps that have keys and values, where keys can be used to retrieve values. 

Major characteristics of HashMaps:

* Cannot have duplicate keys
* Not ordered

To instantiate a HashMap, we use: `Map<String, Integer> hashMapName = new HashMap<>();`

Nested HashMap, where the value is also a HashMap: `Map<String, Map<String, Integer>> hashMapName = new HashMap<>();`
                                                                        
To assign values to keys, we use: `hashMapName.put("Joe", 72);`

*Note:* Assigning an additional value to "Joe" using `put`, would simply replaces the value assigned to the key since we're not allowed to have duplicate keys.

To get size of the HashMap: `hashMapName.size());`

To get a specific value, given a key: `hashMapName.get("Joe"));`

To replace a value: `hashMapName.replace("Joe",25);`

To remove entries: `hashMapName.remove("Joe");`

There are several ways to display the content of a HashMap:

1. Using a key set
1. Using a collection of values
1. Additional way: Using Entry Sets

**First, using a key set:**

	//Create a set of all keys
	Set<String> keys = hashMapName.keySet();
	
	//Use enhanced for loop to printout all keys and corresponding values
	for(String key: keys){
		System.out.println("Map keys: " + key + " - Map values: " + hashMapName.get(key));
	}

**Second, using a collection of values:**

        //Create a collection of all values
        Collection<Integer> values = hashMapName.values();

		//Use enhanced for loop to printout all values
        for(Integer value : values){
            System.out.println("Map values: " + value);
        }

**Finally, using Entry Sets:**

        Set<Map.Entry<String, Integer>> myEntries = hashMapName.entrySet();

        for (Map.Entry<String, Integer> entry: myEntries){
            System.out.println("Map keys: " + entry.getKey() + " - Map values: " + entry.getValue());
        }
		
# Exceptions

**Types of Exceptions:**
* Checked: We are required to either catch these or specify that our code might throw one of these. The compiler will enforce this requirement.
* Unchecked: We do not have catch or specify these, but we can catch them if we want to.

**Handling Exceptions:**
There are two ways to address code that might throw an exception:
* We can handle them—we call this catching the exception.
  * We use: `try...catch, finally`
* We can pass the buck by marking that our code also might throw and exception, leaving it to other code to catch the exception.
  * For instance, we can add `throws IOException` after a method's signature to leave it to other code to catch exceptions in the method.
  
**Most Common Exceptions:** https://docs.oracle.com/javase/8/docs/api/index.html?java/lang/Exception.html
* `Exception`
* `NumberFormatException`
* `ArrayIndexOutOfBoundsException`
* `FileNotFoundException`
* `IOException`

### Try... Catch & Throw (https://www.w3schools.com/java/java_try_catch.asp)	
		
	try {
	  // Block of code to try
	} catch(Exception e1) { 
	  // Block of code to handle errors
	} catch(Exception e2) { 
	  // Block of code to handle errors
	} finally {
	  // lets you execute code, after try...catch, regardless of the result
	}

*Note: To handle multiple exceptions in the same catch block, we can use the following format: `(Exception | IOException e)`.*
	
# Printing & Reading From Files:

Example available at: https://github.com/Ahmed3lmallah/Workplace/tree/master/csv

**Different types of files that Java can handle:**

1. csv [Comma Separated Values]
1. json [Java Script Object Notation]
1. xml [eXtensible Markup Language]

*Note: All the following codes should be included inside Try..Catch blocks since exceptions are common when writing or reading from files*

Common exceptions when dealing with files:
1. JsonProcessingException
1. IOException

## 1. CSV:

### First we need to add openCsv dependency to the pom file:

	<dependency>
		<groupId>com.opencsv</groupId>
		<artifactId>opencsv</artifactId>
		<version>4.4</version>
	</dependency>

### Manually Reading From File into an Array:

	//A Scanner that reads from the file
	Scanner scanner = new Scanner(new BufferedReader(new FileReader("fileName.csv")));
	
	//A String that holds .nextLine from the file
    String currentRow = "";
	
	//String arrays that will hold elements of each line
    String[] headings = new String[0];
    String[] currentCells = new String[0];

	//Read the first line (if it exists)
	if (scanner.hasNext()) {
		currentRow = scanner.nextLine();
		
		//Split the line String Where Commas exist into elements
		headings = currentRow.split(",");
		
		//We then use While(scanner.hasNext) for following Lines
	}

### Using the array to make Objects:

	//Creating a List of Objects
	List<Class> nameOfList = new ArrayList<>();
		
	while (scanner.hasNext()) {
		currentRow = scanner.nextLine();
		currentCells = currentRow.split(",");

		//Creating an object and using array elements to set the properties
		Class currentObject = new Class();
		currentObject.setProperty(currentCells[0]);
		
		nameOfList.add(currentObject);
	}

### Automatically Reading From File into an Array using OpenCSV:
	
	//Automatic CSV Reader
	CSVReader reader = new CSVReader(new FileReader("fileName.csv"));

	//String arrays that will hold elements of each line
	String[] currentCells = new String[0];
	String[] headings = new String[0];
		
	//Read the first line (if it exists)
	//No Split Needed
	headings = reader.readNext();
	
	//Read the Reminder of the file
	while ((currentCells = reader.readNext()) != null) {
                //Do something with eachline, e.g. print or store into a List of Objects 
            }

### Automatically Reading From File into an Object using OpenCSV:

*Note: We first need to create the class for the object and anotate each property as follows:*

`@CsvBindByName(column = "Property")`

	List<ClassType> nameOfList;

	nameOfList = new CsvToBeanBuilder<ClassType>(new FileReader("fileName.csv")).withType(ClassType.class).build().parse();

That automatically creates a list of objects of the ClassType.

### Writing into a CSV file:

	Writer writer = new FileWriter("fileName.csv");
	
    StatefulBeanToCsv beanToCsv = new StatefulBeanToCsvBuilder(writer).build();
	
    beanToCsv.write(nameOfList);
	
    writer.close();

## 2. .JSON:

### First we need to add Jackson dependency to the pom file:

	<dependency>
		<groupId>com.fasterxml.jackson.core</groupId>
		<artifactId>jackson-databind</artifactId>
		<version>2.8.10</version>
	</dependency>
	<dependency>
		<groupId>com.fasterxml.jackson.dataformat</groupId>
		<artifactId>jackson-dataformat-xml</artifactId>
		<version>2.8.10</version>
    </dependency>

### Reading From JSON into an Object using Jackson:

	ObjectMapper mapper = new ObjectMapper();

    List<ClassType> nameOfList;

    nameOfList = mapper.readValue(new File("fileName.json"), new TypeReference<List<ClassType>>(){});
	
**Note: We should avoid having a constructor in ClassType, or else we will get exceptions.**

### Writing into a JSON file:

Assuming we already have a list, called nameOfList, of Objects:

	ObjectMapper mapper = new ObjectMapper();
	
	String jsonList = mapper.writeValueAsString(nameOfList);

	System.out.println(nameOfList);
	
	PrintWriter writer = null;

	writer = new PrintWriter(new FileWriter("fileName.json"));

	writer.println(nameOfList);
	
	if (writer != null) {
		writer.flush();
		writer.close();
	}

## 3. .XML:

### First we need to add Jackson dependency to the pom file:

*Note: this is the same as .JSON dependencies*

	<dependency>
		<groupId>com.fasterxml.jackson.core</groupId>
		<artifactId>jackson-databind</artifactId>
		<version>2.8.10</version>
	</dependency>
	<dependency>
		<groupId>com.fasterxml.jackson.dataformat</groupId>
		<artifactId>jackson-dataformat-xml</artifactId>
		<version>2.8.10</version>
    </dependency>

### Reading From XML into an Object using Jackson:
	
	ObjectMapper mapper = new XmlMapper();

	List<ClassType> nameOfList;

	nameOfList = mapper.readValue(new File("fileName.xml"), new TypeReference<List<ClassType>>(){});        

**Note: We should avoid having a constructor in ClassType, or else we will get exceptions.**

### Writing into an XML file:

Assuming we already have a list of Objects, called nameOfList:

	ObjectMapper mapper = new XmlMapper();
	
	String xmlList = mapper.writeValueAsString(nameOfList);

	System.out.println(xmlList);

	writer = new PrintWriter(new FileWriter("fileName.xml"));

	writer.println(xmlList);
	
	if (writer != null) {
		writer.flush();
		writer.close();
	}
	
## Java Functional API

`list.replaceAll(lambda)` -- calls the lambda once for each item in the list, storing the result back into the list (or other type of collection). 
e.g. `nums.replaceAll(n -> n * 2);`

`list.removeIf(lambda)` -- calls the lambda once for each item in the collection, removing each item where the lambda returns true. 
e.g. `nums.removeIf(n -> n < 0);`

Simple Lambda Examples -- the data types are inferred from the context and from the type of the expression following the "->":

`n -> n * 2` -- takes Integer, returns Integer 

`n -> n < 0 && n >= -10` -- takes Integer, returns boolean 

`s -> s.length()`  -- takes String, returns Integer 

`s -> s.startsWith("hi")` -- takes String, returns boolean

### Java Streams

The Java stream system provides more complicated lambda features. The stream calls do not modify the original list, returning a new data structure of the results. Note that the boolean logic of `filter()` is the opposite of `removeIf()`.

**Major methods:**
`.stream()` creates a stream out of a list

`.map(n -> n*2)` similar to replaceAll

`.filter`

`.forEach`

`.collect(Collectors.toList());` store results in a new list

**Example 1.** Creating a stream, mapping each Integer in the stream, then filtering and adding to the same list:

	List<Integer> listName = -something-;
	listName = listName.stream()
		.map(n -> n * 2)
		.filter(n -> n >= 0)
		.collect(Collectors.toList());

**Example 2.** Creating a stream, filtering, then doing something for each filtered object:
	
	List<Object> listName = -something-;
	listName
		.stream()
		.filter(b -> b.getMake().equals(make))
		.filter(bike -> bike.getWeight() < weight)
		.forEach(bike -> {
			System.out.println("Make: " + bike.getMake());
			System.out.println("Model: " + bike.getModel());
		});
	
**Example 3.** Creating a stream, filtering, then storing into a new list:
	
	List<Object> newListName =
        listName
			.stream()
			.filter(bike -> bike.getWeight() < weight)
			.collect(Collectors.toList());
			
**Example 4.** Creating a stream, then grouping objects into a new Map:
	
	Map<String, List<Object>> mapName =
		listName
			.stream()
			.collect(Collectors.groupingBy(b -> b.getMake()));

**Example 5.** Getting maximum or average:

	double avgHorsepower =
		bikes
			.stream()
			.mapToInt(b -> b.getHorsepower())
			.average()
			.getAsDouble();

	int maxHorsePower =
		bikes
			.stream()
			.mapToInt(bike -> bike.getHorsepower())
			.max()
			.getAsInt();			
	
# Useful Code 

### MATH: https://docs.oracle.com/javase/8/docs/api/java/lang/Math.html
		

### Recursion (https://www.java-samples.com/showtutorial.php?tutorialid=151)
Calling the method from inside the method:

	int fact(int n) {
		int result;
		if ( n ==1) return 1;
		result = fact (n-1) * n;
		return result;
		}

# GIT:

	Git clone
	Git checkout -b "branch name" : only use -b to add new branch
	Git add -A : -A for all files
	Git commit -m "Comment" 
	Git push origin "branch name"
	Git pull

# BASH:

	$ cd ~
	$ cd ..
	$ cd "child folder"
	$ mkdir "new folder"
	$ touch "new file"
	$ ls
	$ pwd
	$ explorer .

# SQL:

	CREATE DATABASE **database_name**;

	USE **database_name**;
	CREATE TABLE **table_name** (
	  id INT AUTO_INCREMENT NOT NULL,
	  Title VARCHAR(250) NOT NULL,
	  Author VARCHAR(250) NOT NULL,
	  In_stock BOOLEAN DEFAULT TRUE,
	  Quantity INT,
	  PRIMARY KEY (id)
	  );

	USE **database_name**;
	INSERT INTO **table_name** (title, author, quantity) VALUES ('Title 1','Author 1',19);
	UPDATE **table_name** SET quantity = 10 WHERE ID=2;
	DELETE FROM **table_name** WHERE id = 3;
	SELECT * FROM **table_name**;
	SELECT title, author FROM **table_name**;
