In many things, [[Java]] is like [[C]] in terms of syntax.

# Primitive Types

Primitive types are declared with the same syntax:

``` java
int n = 1;
char c = 'a';
double nf = 1.5;
```

But Java have a Boolean type:

``` java
boolean bool =  true;
```

# Complex Types

Complex types are classes in Java. The most used complex value is the **Strings**.
To use them, declare:

```java
String son = "Arthur";
```

# Arrays

with arrays, is almost the same:

```java
int[] n = [1, 2, 3, 4]; // in C: int n[] = {1, 2, 3, 4};

//to get a value
n.get(0); // == Elissandro

//you can't remove a value

//to get the length
n.length; // print 4
```

But Java have a dynamic type of array, called Array List, it is a **complex type**:

```java
ArrayList<String> n = new ArrayList<>();

//To add a value
n.add("Elissandro");
n.add("Luana");
n.add("Arthur");

//to get a value
n.get(0); // == Elissandro

//to remove a value
n.remove(0); // remove Elissandro
n.remove("Elissandro");

//to get the length
n.size();
```

Is important to remember the **Array List don't work with primitive values**. To use them in Array Lists, the **wrapper classes** - that are complex types also - are needed:

| **Primitive** | **Wrapper Class** |
| ------------- | ----------------- |
| `int`         | `Integer`         |
| `double`      | `Double`          |
| `char`        | `Character`       |
| `boolean`     | `Boolean`         |
Example:
```java
ArrayList<Integer> n = new ArrayList<>();

//To add a value
n.add(30);
n.add(27);
n.add(1);

//to get a value
n.get(0); // == 30

//to remove a value
n.remove(0); // remove 30
n.remove(Integer.valueOf(30));
```

# Conditionals

The syntax is like the C syntax:
```java
int i = 1;
int j = 0;

if (i) {
	System.out.println("TRUE");
}

if (j) {
	System.out.println("TRUE");
} else {
	System.out.println("FALSE");
}
```

# Loops

Again, is the same as in C:

## For:

```java
for (int i = 0; i < 10; i++) {
	System.out.println(i);
}
```

## While:

```java
int i = 0;
while (i < 10) {
	System.out.println(i);
	i++;
}
```

## Do-while`

```java
int i = 0;
do {
	System.out.println(i);
	i++;
} while (i < 10);
```

## Foreach

Technically, the Java don't have a foreach loop. But it uses for as foreach:

```java
int[] numbers = {1, 2, 3, 4, 5};
for (int num : numbers) {
    System.out.println(num);
}
```

# Casting

```java

//int >> double
double n1 = 30.0;
int n2 = (int)n1;

//Strings >> int
String n3 = "27";
int n4 = Integer.ParseInt(n3);

//int >> String
int n5 = 1;
String n6 = String.valueOf(n5);
```

# Compilation

```zsh
javac Main.java // Compila pra .class - Gera um Main.class
java Main // Executa o arquivo Main.class na JVM
```

# OOP in Java

The OOP in Java is the standard [[Basic about OOP]]. But we have some stuff that is exclusive for Java, let's look up at these.

## Constructors

It is not exclusive from Java, [[Csharp]] is an example, but is closely linked with the language.
It is a **method that build something** just when the class is instantiated, creating a object.

```java

class Car {
	public Car () {
		System.out.println("New car...");
	}
}

Car vw = new Car(); // In the execution, the program will print "New car..."
```

It is important because when you use the constructor method, the attributes defined as parameters in the method should be typed. Like these example bellow:

```java
class Car {  
    private final String model;  
    private final String color;  
    private final double engine;  
  
    public Car (String model, String color, double engine) {  
        this.model = model;  
        this.color = color;  
        this.engine = engine;  
    }  
    public String getModel () {  
        return model;  
    }
    public String getColor () {  
        return color;  
    }  
    public double getEngine () {  
        return engine;  
    }
```

## Methods

Your main class, needs a method called main. This is like the main function in [[C]].

```java
public class Main {  
  
    public static void main(String[] args) {  
        Car mycar = new Car("golf gti", "nardo grey", 2.0);  
		
        System.out.println("The car model is: " + mycar.getModel);  
    }  
}
```

# Packages

Is like [[Csharp]] [[Namespace]]. But in Java, the package needs follow the directory file path.
So, it is also a logic and physical organization.

```java
package carro //It need to be in a directory called car

public class Main {  
  
    public static void main(String[] args) {  
        Car mycar = new Car("golf gti", "nardo grey", 2.0);  
		
        System.out.println("The car model is: " + mycar.getModel);  
    }  
}
```
# Access Modifiers

| `public`    | Is accessible in all program, even in another packages               |
| ----------- | -------------------------------------------------------------------- |
| `private`   | Only visible inside a parent class                                   |
| `protected` | Visible in the package or in sub-classes                             |
| `default`   | Is used when none access modifier is declares. It is package private |
## Where is this used?

| Element                                                | `public` | `protected` | `default` | `private` |
| ------------------------------------------------------ | -------- | ----------- | --------- | --------- |
| **Top-level Classes<br>(The class with the filename)** | ✅        | ❌           | ✅         | ❌         |
| **Nested Classes**                                     | ✅        | ✅           | ✅         | ✅         |
| **Methods**                                            | ✅        | ✅           | ✅         | ✅         |
| **Atributtes**                                         | ✅        | ✅           | ✅         | ✅         |
| **Constructors**                                       | ✅        | ✅           | ✅         | ✅         |

# Interfaces

Are two ways to declare an interface.
1. Top-level interface(most indicate way):
```java
// file: Vehicle.java
public interface Vehicle {
    void run();
    void brake();
}
```

2. Nested Interface(Inside a class):
```java
public class Car {

    interface Engine {
        void TurnOn();
    }
}
```

The first is always public, and the nested can be `private`, `protected`, `default` or `public`.

# Abstract Class

A abstract class is like a "buffered interface". It can't be instantiated like a interface, but we can implement methods inside them and other classes can inherit this one.

```java
abstract class Vehicle {
    String brand;
    String model;

    public Veiculo(String brand, String model) {
        this.brand = brand;
        this.model = model;
    }
	
    // Abstract method abstrato: the child class can implement
    public abstract void run();
	
    // Concrete method: Is implemented
    public void mostrarInfo() {
        System.out.println("Brand: " + brand + ", Model: " + model);
    }
}
```

# Exceptions

The most common exceptions are:
- `NullPointerException` - When a null memory value is accessed;
- `ArrayOutOfBoundsException` - When the memory value excedes the array bounds;
- `RuntimeException` - General exceptions;
- `IOException` - Input/Output exception

To deal with these exceptions, the **Try Cath** Expression is used:
```java
try {
    car.run();
} catch (RuntimeException exception){
	System.out.println("There are an exception");
}
```

# Collections

Is a powerful framework that allow you to work with collections(groups of data) in a more easiest way.

## Main Components of the Java Collections Framework

**Interfaces (contracts):**
- `Collection<E>`: The root interface for almost all collections (lists, sets, queues).
- `List<E>`: An ordered collection that allows duplicate elements.  
    _Examples: ArrayList, LinkedList_
	
- `Set<E>`: A collection that does **not** allow duplicate elements.  
    _Examples: HashSet, TreeSet_
    
- `Queue<E>`: A FIFO (First-In, First-Out) structure.  
    _Examples: LinkedList (also implements Queue), PriorityQueue_
	
- `Deque<E>`: A double-ended queue (you can enqueue/dequeue from both ends).  
    _Example: ArrayDeque_
    

> **Note:** `Map<K, V>` does **not** extend `Collection`, but it's part of the framework. It maps keys to values, like **Javascript Objects**, or the **[[Csharp]] Dictionaries**.  
> _Examples: HashMap, TreeMap, LinkedHashMap_


**Implementations (concrete classes):**

Each interface has multiple implementations, each with different performance and ordering characteristics:

- **ArrayList**: Fast index-based access; resizes by copying the underlying array.
```java
List<String> mylist = new ArrayList<>();

//Add
mylist.add("Elissandro");
mylist.add("Luana");
mylist.add("Arthur");
mylist.add("Arthur"); //Work!

//print list
System.out.println(mylist);
```

- **LinkedList**: Fast for inserting/removing elements in the middle; slower index-based access.
```java

//Linked list as a queue
Queue<Strings> myqueue = new LinkedList<>();

//Add
myqueue.add("Elissandro");
myqueue.add("Luana");
myqueue.add("Arthur");

//get the first node and remove it from the list
myqueue.poll();

//get the first node without remove it from the list
myqueue.peek();

//print list
System.out.println(myset);

//------
//Linked list as a linked list
LinkedList<Strings> mylinkedlist = new LinkedList<>();

//Add
mylinkedlist.add("Elissandro");
mylinkedlist.addFirst("Luana");
mylinkedlist.addLast("Arthur");

//Get
mylinkedlist.getFirst();
mylinkedlist.getLast();

//Poll
mylinkedlist.pollFirst();
mylinkedlist.pollLast();
```

- **HashSet**: No ordering guarantee; very fast for searches(O(1)) and insertions (uses hash table).
```java
Set<Strings> myset = new HashSet<>();

//Add
myset.add("Elissandro");
myset.add("Luana");
myset.add("Arthur");
myset.add("Arthur"); //don't work!

//print list
System.out.println(myset);
```

- **TreeSet**: Keeps elements sorted (uses red-black tree); O(log n) for search/insertion.
    
- **HashMap**: Fast key-value mapping with no guaranteed order.
    
- **LinkedHashMap**: Maintains insertion order (or access order if configured).
    
- **PriorityQueue**: A queue with element priorities (backed by a heap).


**Utilities:**

- **Collections** (utility class) — Static methods for sorting, searching, synchronization, etc.
- **Arrays** — Some helper methods for "array collections" (e.g., converting arrays to lists).

# Generics
It allow you to write code that works with any type in a type-safe way. Instead of using `Object` and relying on casting, generics let the compiler ensure that you’re using the correct types. This makes your code safer and clearer.

```java
List<String> names = new ArrayList<>();
```

## Bounded Generics

You can **restrict** the types that can be used with generics using bounds, like`T extends SomeClassOrInterface`.

This means the type `T` must be a subclass of `SomeClassOrInterface`, or implement that interface.

```java
public interface Paintable {
    void paint();
}
```

So we can do this:

```java
public class Painter<T extends Paintable> {
    private T item;
    
    public void paint() {
        item.paint();
    }
}
```

# Records
A `record` is **an immutable class by default**.
When you declare a `record`, the compiler automatically:

- Creates **`private final` fields** for each component.
- Generates **getters**, **`equals()`**, **`hashCode()`**, and **`toString()`** methods.
- Does **not** create setters — meaning you can't change the values after the object is created.

```java
//declaration
public record Person(String name, int age) {}

//implemantation
Person PersonA = new Person("Arthur",1);

//getters
PersonA.name();
PersonA.age();
```

Records are most used when we create DTO's(Data Transfer Objects) or POJO's(Plain old Java Objects).