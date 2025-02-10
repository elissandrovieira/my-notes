C# is a statically-typed language, which means that everything has a type at compile-time. Assigning a value to a name is referred to as defining a variable. A variable can be defined either by explicitly specifying its type, or by letting the C# compiler infer its type based on the assigned value (known as _type inference_). Therefore, the following two variable definitions are equivalent:

```csharp
int explicitVar = 10; // Explicitly typed
var implicitVar = 10; // Implicitly typed
```

Updating a variable's value is done trough the `(=)` operator. Once defined, a variable's type can never change.

```csharp
var count = 1; // Assign initial value
count = 2;     // Update to new value

// Compiler error when assigning different type
// count = false;
```

C# is an [object-oriented language](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/concepts/object-oriented-programming) and requires all functions to be defined in a _class_. The `class` keyword is used to define a class. Objects (or _instances_) are created by using the `new` keyword.

```csharp
class Calculator
{
    // ...
}

var calculator = new Calculator();
```

A function within a class is referred to as a [[Method]]. Each method can have zero or more parameters. All parameters must be explicitly typed, there is no type inference for parameters. Similarly, the return type must also be made explicit. Values are returned from methods using the `return` keyword. To allow a method to be called by code in other files, the `public` access modifier must be added.

```csharp
class Calculator
{
    public int Add(int x, int y)
    {
        return x + y;
    }
}
```

Methods are invoked using dot (`.`) syntax on an instance, specifying the method name to call and passing arguments for each of the method's parameters. Arguments can optionally specify the corresponding parameter's name.

```csharp
var calculator = new Calculator();
var sum_v1 = calculator.Add(1, 2);
var sum_v2 = calculator.Add(x: 1, y: 2);
```

If the method to be called is defined in the same class as the method that calls it, the class name can be omitted.

If a method does not use any object _state_, the method can be made _static_ using the `static` modifier. Static methods are also invoked using dot (`.`) syntax, but are invoked on the class itself instead of an instance of the class.

If a class only has static methods, it too can be made static using the `static` modifier. This expresses the intention of the class.

```csharp
static class Calculator
{
    public static int Multiply(int x, int y)
    {
        return x * y;
    }
}

Calculator.Multiply(2, 4); // => 8
```

Scope in C# is defined between the `{` and `}` characters.

C# supports two types of [comments](https://www.w3schools.com/cs/cs_comments.asp). Single line comments are preceded by `//` and multiline comments are inserted between `/*` and `*/`.

Integer values are defined as one or more (consecutive) digits and support the [default mathematical operators](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/operators/arithmetic-operators#addition-operator-).

A variable name [must follow some rules](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/inside-a-program/identifier-names) like starting either by a letter or an underscore, and [should follow C# naming convention](https://docs.microsoft.com/en-us/dotnet/standard/design-guidelines/naming-guidelines). If a variable name collides with a reserved [C# keyword](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/), it must be escaped using `@`. Use of that notation is not recommended, but it can be encountered in exceptional cases, for example: `var @this`, `var @class` or `var @var`.

There are a couple of concepts that are so fundamental to a C-family language like C# that they occur naturally in almost any piece of non-trivial code. These are [[Mutation]] and [[Scope]]. Mutation is the idea that a variable can have its value changed in the course of a program's lifetime. Scope is the idea that the value associated with a name (of a program element) is only accessible within the code "area" where it is defined. The principal code areas in C# are _class/struct_ and _function_ (typically methods) but can also include the bodies of loops and other constructs.

### Learn More
- [var](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/var)
- [assignment](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/operators/assignment-operator)
- [classes](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/classes#declaring-classes)
- [methods](https://docs.microsoft.com/en-us/dotnet/csharp/methods)
- [return](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/return)
- [comments](https://www.w3schools.com/cs/cs_comments.asp)
- [operators](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/operators/arithmetic-operators#addition-operator-)
- [variable-names](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/inside-a-program/identifier-names)
- [naming-guidelines](https://docs.microsoft.com/en-us/dotnet/standard/design-guidelines/naming-guidelines)
- [csharp-keywords](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/)