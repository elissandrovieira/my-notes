# C# Scope of Variables

The part of the program where a particular variable is accessible is termed the ****Scope of that variable.**** A variable can be defined in a class, method, loop, etc. In C/C++, all identifiers are lexically (or statically) scoped, i.e., the scope of a variable can be determined at compile time and is independent of the function call stack. But C# programs are organized in the form of classes.

So, C# scope rules of variables can be divided into three categories as follows:

- Class Level Scope
- Method Level Scope
- Block Level Scope

### 1. Class Level Scope

Declaring the variables in a class but outside any method makes them directly accessible anywhere in the class. These variables are also termed as fields or class members.

- Class level scoped variables can be accessed by the non-static methods of the class in which they are declared.
- The access modifier of class level variables doesn’t affect their scope within a class.
- Member variables can also be accessed outside the class by using the access modifiers.

***Example:***

``` c#
// C# program to illustrate the
// Method Level Scope of variables
using System;
  
// Declaring a Class
class Geeks { 
  
    // Declaring a method
    public void display()
    { // From here, method level scope starts
  
        // This variable has
        // method level scope
        int m = 47;
  
        // Accessing method level variable
        Console.WriteLine(m);
  
    } // Here method level scope ends
  
    // Declaring another method
    public void display1()
    { // From here, method level scope starts
  
        // This will give compile-time error as
        // 'm' is not accessible outside 'display()' method
        // Console.WriteLine(m); // Uncommenting this line will cause an error
  
    } // Here method level scope ends
  
} 

```

### 2. Method Level Scope

Variables that are declared inside a method have method level scope. These are not accessible outside the method. However, these variables can be accessed by the nested code blocks inside a method.

- These variables are termed as local variables.
- There will be a compile-time error if these variables are declared twice with the same name in the same scope.
- These variables don’t exist after the method’s execution is over.

***Example:***

```c#
// C# program to illustrate the
// Method Level Scope of variables
using System;
  
// Declaring a Class
class Geeks { 
  
    // Declaring a method
    public void display()
    { // From here, method level scope starts
  
        // This variable has
        // method level scope
        int m = 47;
  
        // Accessing method level variable
        Console.WriteLine(m);
  
    } // Here method level scope ends
  
    // Declaring another method
    public void display1()
    { // From here, method level scope starts
  
        // This will give compile-time error as
        // 'm' is not accessible outside 'display()' method
        // Console.WriteLine(m); // Uncommenting this line will cause an error
  
    } // Here method level scope ends
  
} 
```

### 3. Block Level Scope

These variables are generally declared inside the for, while, or other statements.

- These variables are also termed as loop variables or statement variables as they have limited scope within the body of the statement in which they are declared.
- A loop inside a method generally has three levels of nested code blocks (i.e., class level, method level, loop level).
- The variable which is declared outside the loop is also accessible within the nested loops. It means a class level variable will be accessible to the methods and all loops. A method level variable will be accessible to loops inside that method.
- A variable which is declared inside a loop body will not be visible outside the loop body.

***Example:***

```c#
// C# code to illustrate the Block
// Level scope of variables
using System;
  
// Declaring a Class
class Geeks
{ 
  
    // Declaring a method
    public void display()
    { 
  
        // This variable has
        // method level scope
        int i = 0;
  
        for (i = 0; i < 4; i++) {
          
            // Accessing method level variable
            Console.WriteLine(i);
        }
  
        // Here j is a block level variable
        // It is only accessible inside
        // this for loop
        for (int j = 0; j < 5; j++) {
          
            // Accessing block level variable
            Console.WriteLine(j);
        }
  
        // This will give an error as block level
        // variable can't be accessed outside
        // the block
        // Console.WriteLine(j); // Uncommenting this line will cause an error
  
    }
  
} 
```