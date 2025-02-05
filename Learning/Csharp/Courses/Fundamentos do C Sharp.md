# WHY I WOULD USE C#?

## About C# ##
- A programming language
	- Typed;
	- Compiled and
	- Managed.
- Created by Andres Hejlsberg in 2001
- Is the primary language of Microsoft

## Why learn C#?
- Complete language
- Maturity
- Market
- Community
- Applicability
- Microsoft Background
- Object-oriented

## Runtime
- The code needs to be executed on the computer's central processing unit(CPU).
- On C# and .NET, the Runtime is called CLR or CLR Runtime.
- Manage memory, security, and other essential resources.
- On C/C++ for example, we need to allocate memory manually.
- Do you know the famous Windows blue screen? It’s happening because the program tries to access a part of the memory dedicated to the system.
- On C# we interact less than the other languages above, or almost don’t interact with the machine resources.

*CLR are the initials for COMMON LANGUAGE RUNTIME.

## COMPILATION AND MANAGEMENT
- Microsoft has other languages like VB.NET, F#, and even Cobol.NET
- Every one of these needs to be supported.
- Code maintenance, fixing bugs, and more.
- When the Microsoft ecosystem was created, it was imagined in this way.
- Support some languages.
- If each language had a manager, it would be so annoying.
- Each language has its compiler.
- The initial compilation generates an intermediary code.
- This language is the Intermediate Language (IL).

``` c
----------------------------
| C#, VB.NET, F#, Cobol.NET |
----------------------------
	|
	v
-------------------------
| Intermadiated Language |
-------------------------
	|
	v
--------------
| Binary Code |
--------------

```

## IL

- Although the compilations are different:
	- The management is the same.
	- Memory allocation;
	- Executing instructions on a processor.
- The CLR gets the code and compiles this in IL.
	- C#, VB.NET, F#, Cobol.NET
- C# and VB.NET files can exist in the same project.
	- But never in the same file.
- The compilation result of IL is always the same.
- The IL conversion process to binary is called JIT( Just in Time)

## FRAMEWORKS
- A framework is a structure, a foundation.
	- A library set.
- Is used as the base to build applications.
	- With this, we don’t need to start at zero.
- This concept exists in many technologies.
- In this course, we will learn about [[.NET]] the Microsoft Framework.
  
## .NET FRAMEWORK
- C# is the language.
- The framework is called .NET.
- The first version was released in 2001.
- It had versions 1.0, 1.1, 2.0, 3.0, 3.5, and 4.X(Now)
- It can be installed side-by-side.
- Only Windows compatibility.
- Considered legacy.

## .NET CORE
- The most recent version of the .NET framework.
- Released in 2015.
- Support other OS, like Linux and Mac.
- The first version supports only the basic features.
	- Core means “núcleo” in Portuguese. 
	- Changing a framework used for millions of people is not easy.
	- It was totally rewritten.
	- It has great retro-compatibility.

## .NET STANDARD
- .NET Framework and .NET core coexist.
	- It can be installed together, side-by-side.
	- It can be used in the same project.
- How do we guarantee that something we code will run in both?
	- With .NET Standard.
- .Net Standard isn't a framework, is just a contract.
	- Called Surface API.
- It is the intersection between both frameworks.


```c

- - - - - - - - - - - - - - - - - -
-                + + + + + + + + +-+ + + + + + + +
- LEGACY SYSTEM  + .NET Standard  -   NEW SYSTEM +
- .NET Framework +                -   .NET Core  +
- - - - - - - - -+- - - - - - - - -              +
                 + + + + + + + + + + + + + + + + +

```
  
```c
APP MODELS
 --------------------- ------------------- -----------
|    .NET FRAMEWORK   |     .NET CORE     |  XAMARIN  |
 --------------------- ------------------- -----------
| WPF | WINDOWS FORMS | UWP | ASPNET.Core | iOS | OS X|
|        ASP.NET      |                   |  Android  |
 --------------------- ------------------- -----------
|                .NET STANDARD LIBRARY                |
|             One library to rule them all            |
 -----------------------------------------------------
 |                COMMON INSFRASTRUCTURE              |
 -----------------------------------------------------
|   Compilers   |  Languages  |   Runtime Components  |
 -----------------------------------------------------

```

## .NET 5
- The unification of the frameworks.
- .NET Core reached the .NET Framework in the level of content.
- It doesn’t make sense the two frameworks exist.

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXeTwGdVvWcDCO2U7lLDNRc9kRZhTY5CUFmAjEwXq3nao_DlM-V-jk9S8hL7ZZym2KxdhpSYtIFOyBiR0h788I7WlAhpcTsTcF8idi9U7syxttpGQna-6Fd0ofDdbzBco7CrtZjza3lprhaCq5ali44Msvs?key=YYUytDJBBYVHufu_INawBA)

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXet3Cbp-ZG2cDAKw8YtC5NA_zG80wiRdEgUX4MFSZCDb2MyS03NmhYbvXVoKCEabaR_PUQw8cc1C5593VRFLqz8fh1htZUvIrYRZZpWcFxRLdtjOwZTe1KhvWvLyfLYSv2qbu-Ebh3rsHwXugUZ4-JDjV0T?key=YYUytDJBBYVHufu_INawBA)

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXd3AMT6FlUX8Dy_wYy5RyqeM5JoSWzu8inBpLcBbhOFuoeF4rD7YOXnUNlIUzTOYhqzp_suUOdN5BZSv34fVFPZkDxUVJpkTqqzEvpU38TxjD0phbP01AHyzh8L69vCviIPUy9wlPE1zWbFd63BTLaQ0SnD?key=YYUytDJBBYVHufu_INawBA)

  
  
  

RUNTIME

  

- Is necessary to execute the application.
    
- Divided in 3:
    

- ASP.NET to web applications.
    
- Desktop(.exe) to desktop applications.
    
- .NET Core to any other application.
    

- Console, Batch, Service.
    
- Don’t have an interface.
    

- Also, have versions
    

- The version must be compatible with the codification version.
    

- Used only to deliver applications.
    

- It only executes.
    

- Optimized to execution.
    

  

SDK

  

- Initials to Software Development Kit
    
- Has all we need to develop applications.
    
- Has a runtime integrated.
    
- We don’t use it in production(release).
    

- To production, we need just the runtime.
    

- Is bigger than runtime.
    

  
  
  

.NET - GUIDE

  

CLI

- Initials to Command Line Interface.
    

- Commands added at the terminal
    

  

dotnet CLI

- Defined by command “dotnet”
    

- dotnet --version
    

- Check the dotnet version.
    

- dotnet --list-sdks
    

- List installed SDK’s.
    

- dotnet --list-runtimes
    

- List installed Runtimes.
    

- dotnet --help
    

- List available commands.
    

  
  
  
  
  
  
  
  
  
  
  
  

PROJECTS TYPE

  

- Class Library
    

- The final result is a DLL
    
- Don’t have an interface
    

- Console Application
    

- The final result is an application running at the console(shell)
    
- Can receive data, wait for user’s input
    

- Web Project
    

- ASP.NET Web
    
- ASP.NET MVC
    
- ASP.NET WebAPI
    

- Test project
    

- Microsoft Tests
    

  

CREATE A NEW PROJECT

  

- dotnet cli
    

- dotnet new console => New Console Application
    
- dotnet new classlib=> New Class Library
    
- dotnet new web=> New ASP.NET Core
    
- dotnet new mvc=> New ASP.NET Core
    
- dotnet new webapi=> New ASP.NET Core
    
- dotnet new mstest=> New Microsoft Tests project
    

  

DEFINITIONS

  

- Creating a project is the same as generating the initial application files
    

- It always generates the files in the current folder
    
- To specify the folder we can use the “-o”
    

- dotnet new console -o MyNewFolder
    

  
  
  
  
  

EXECUTION FLOW

  

DEFINITIONS

- dotnet restore
    

- Restore all packages needed for the application to run
    

- dotnet build
    

- Compile the application
    

- dotnet clean
    

- Clean the before compilations
    

- dotnet run
    

- Compile and run the application
    

  
  

ENVIRONMENTS VARIABLES

  

- Is usual to use many environments for the applications
    

- Development
    
- Approval(não sei ao certo se é isso, em português é homologação)
    
- Production
    

- Each environment has its settings
    

- external access keys
    
- Database connections
    

- We can set how the environment we are using at .Net
    

- dotnet run --environment=YourEnvironment
    
- dotnet run --environment=development
    
- dotnet run --environment=production
    

- The run command doesn’t execute the Debug
    

- So, the application doesn’t stop in the Break Points(We are going to explain forward)
    

  

CONSOLE APP STRUCTURE

  

- .csproject file
    

- XML extension
    
- project definitions
    
- It is included at all .NET projects
    

- Program.cs
    

- Main file(C#)
    
- Gateway(Porta de entrada)
    
- It is the first that will be run.
    

  

DEBUG

  

Is the act of inspecting the code and looking if is all ok.

To Debug in VS Code we use this button ![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcEEacTWiBbF1s5WhNxXCuwLa-_weXU8oWlC-Y1xXb3tweWbIzrfFbv20Jl3kb5h0Ze5dQVfLlE9pt0rA1vYeIk62EIMMdFue8ATX9CeBmo8s95FqWnPA3c2FIgFPom8ewsasXQ13AEnvSU3Dj4tLjMqcGF?key=YYUytDJBBYVHufu_INawBA)

  
  
  
  
  
  
  

SCOPE OF THE APPLICATION

  

- Imports
    
- Namespace
    
- Class
    
- Main method
    

Example:

  

|   |
|---|
|Program.cs|
|using System; // Imports<br><br>namespace MyApp // Namespace - Logical division<br><br>  {<br><br>    internal class Program // Class<br><br>      {<br><br>        static void Main(string[] args) // Main method<br><br>          {<br><br>            Console.WriteLine("Hello World!");<br><br>          }<br><br>      }<br><br>  }|

  

Starting with .NET 6, the project template for new C# console apps generates the following code in the Program.cs file:

  

|   |
|---|
|Program.cs|
|// See https://aka.ms/new-console-template for more information Console.WriteLine("Hello, World!");|

  

The new output uses recent C# features that simplify the code you need to write for a program. For .NET 5 and earlier versions, the console app template generates the first code box.

  
  

NAMESPACES

  

- Whereas the folders are the fiscal division;
    
- The Namespaces are the logical divisions;
    
- As well as we can’t have two files with the same name in the folder;
    
- We can’t have two classes with the same name inside a Namespace.
    
- The ideal scenario is to have only one Namespace  and one class for file.
    
- The scope of a Namespace is defined between brackets { }.
    

- Classes and methods also
    

- A Namespace can be used again.
    

- It can be inside many files.
    

- The Namespace usually is the same name as the folder.
    
- For the same Namespace in different folders we use dot + folder name. Ex: namespace.folder.
    
- We can create as many Namespaces as we want
    
- Don’t use space or special characters
    
- Every word at Namespace begins with a capitalized word.
    
- We can a Namespace inside the other using “ ”
    
- The imports are made by Namespaces
    

  
  

IMPORT

  

- Imports define what library is used at the project
    
- As standard only the basic is included automatically
    
- Is necessary import what we need to work
    
- It’s done in beginning of the application
    
- The word using is reserved for this.
    

  

IMPORTANT NOTES

- Organize the code in folders and namespaces is crucial
    
- In large applications, the code volume is high
    
- And the people working on the same project too
    
- Understanding this organization is crucial
    

  
  

VARIABLES

  

- Variables storage information
    
- The value of a variable can change at any moment
    

  

DEFINITIONS

- A TYPE or the keyword var can be used to declare a variable
    
- In C# the TYPE is always before the variable name
    
- The value can be informed when the variable is declared
    
- If the value don’t be informed, the standard value is applied
    
- When var word is used, the value must be informed
    
- The first letter at the variable is always in lowercase
    
- EX:
    

  

|   |   |
|---|---|
||init age; // Right, start in zero<br><br>init age = 25; // Right, start in 25<br><br>var age = 25; // Right, start in 25<br><br>var age; // Wrong, type don’t declared|

  
  

CONSTANTS

  

- Constants also storage information
    
- Can’t be changed
    
- At declaration is needed inform the value
    
- It is more optimized than variables
    
- Recommended to frequently use
    
- The constants usually are in uppercase
    
- EX:
    

  
  

|   |   |
|---|---|
||const init MINIMUN_AGE; // Right, start in zero<br><br>const init age = 25; // Right, start in 25<br><br>const var age = 25; // Wrong<br><br>const var age; // Wrong|

  
  
  
  

KEYWORDS

  

- It are words of C# exclusive use
    
- This word can’t be used at variables or constants names
    

  
  

COMMENTS

  

- In many scenarios we need put a message at the code
    
- This message shouldn’t executed for the application
    
- Also, is usual use comments in lines we don’t want execute
    
- The comments can be:
    

- One line comment
    
- Multiple line comment
    
- XLM(Metadata)
    

- In VS Code we can comment with CTRL + K + C or  CTRL + K+ U
    

  
  

|   |   |
|---|---|
||// One line comment<br><br>  <br><br>/*<br><br>  Multiple line comment<br><br>*/<br><br>  <br><br>///XML Annotation - (Metadata)|

  
  

PRIMITIVE TYPES

  

- Also called built-in types
    
- It are base types that other types(cmplex) will be derivative.
    
- Defining the correct type, optimizes the application execution.
    
- Are called Value Types.
    
- Storaging the value, not the reference for an item in memory.
    
- It is classifying in:
    

- Simple Types
    
- Enums
    
- Structs
    
- Nullable Types
    

- Each primitive type has one capacity.
    
- If the capacity exceeds, the application reports an error.
    
- This predefined capacity helps in the application optimization
    
- For example, the capacity for the int we used before:
    

- -2,147,483,648 to 2,147,483,647
    

  
  
  
  
  
  
  
  
  
  

SYSTEM

  

- At .NET every start in a base type called system.
    
- All types, since built-in even complex derivates from it.
    
- It is the base for all objects into .NET.
    
- We don’t need to worry about using it.
    
- The use is implicit.
    

  
  

BYTE

  

- It is used to represent a real byte.
    
- In some cases, is required the byte chain of a file for example.
    

- Also called byte array.
    

- Also exist the sbyte, which allows negative values.
    
- The s in sbyte meaning signed(-), and the byte is unsigned.
    

  

DEFINITION

- byte (8-bit)
    

- 0 to 255
    

- sbyte (8-bit)
    

- -128 to 127
    

  
  

INTEGRAL NUMBERS

  

- It means without a point, are defined for the types:
    

- short / ushort
    
- int / uint
    
- long / ulong
    

- Like the signed in bytes, in the numbers for the standard allows negative values.
    
- So we use the unsigned(u) to define this type and don’t receive negative values.
    
- The int type is the most common to be funded.
    

  

DEFINITIONS

- short (16-bit)
    

- -32,768 to 32,767
    

- ushort (16-bit)
    

- 0 to 65,535
    

- int (32-bit)
    

- -2,147,483,648 to 2,147,483,647
    

- uint (32-bit)
    

- 0 to 4, 294, 967, 295
    

- long (64-bit)
    

- -9,233,372,036,854,775,808 to 9,233,372,036,854,775,807
    

- ulong (64-bit)
    

- 0 to 18,446,744,073,709,551,615
    

  
  
  
  
  
  

REAL NUMBERS

  

- Are the numbers that need more precision, it means, punctuation.
    

- float (F Notation)
    
- double
    
- decimal (M Notation)
    

- It has positive and negative numbers, so we don’t need to use signed/unsigned.
    
- The double is the standard type.
    

  
  

|   |
|---|
|*PS|
|F or M Notation means we need to put an f or m letter to indicate that number. Ex:<br><br>  <br><br>float money = 2.500 // Wrong<br><br>float money = 2.500f // Right<br><br>  <br><br>decimal money = 2.500 // Wrong<br><br>decimal money = 2.500m // Right|

  
  

BOOLEAN

  

- It stores only true or false.
    
- Is defined as a bool keyword.
    
- bool (8-bit).
    

- true or false.
    

  
  

CHAR

  

- It is used to store only one Unicode character.
    
- Defined to char keyword.
    
- the attribution of a char value is with single quotation marks.
    
- char (16-bit).
    

- Any character.
    

  
  

STRING

  

- It stores a character's chain.
    
- We can think about this as a list of char.
    
- Desfined to stringg keyword.
    
- the attribution of a char value is with double quotation marks.
    
- string (?).
    

- A character’s chain.
    

  
  
  
  
  
  
  
  

VAR

  

- It replaces any name of type.
    
- It type matches with the first value attributed to this.
    
- Its use is recommended.
    

- Use when you already know well all types.
    

  
  

OBJECT

  

- A generic type that receives any value or object.
    
- Used in cases when we don’t know the information or the information has different types.
    
- Don’t have intelisence (IDE Help).
    
- Avoid!
    

  
  

NULLABLE TYPES

  

- Is an empty type.
    
- Different from zero or an empty string.
    
- All sorts of types, primitive or complex can receive the null value.
    
- The type should be marked as Nullable Type.
    
- The null can be attributed to an object.
    
- Since the object is marked as nullable.
    

- Using a question mark after the type.
    

- If a requirement to a null value is done, an error will be shown.
    

  
  

|   |   |
|---|---|
||int? age = null|

  
  

ALIAS

  

- Alias is like a nickname for all sorts of types at .NET.
    
- For example:
    

- System.String has the alias string. In the code, we use the alias.
    

  
  

STANDARD VALUES

  

- All built-in types have a standard value
    
- If there is no value informed, the standard value is used.
    

- int - 0
    
- float - 0
    
- decimal - 0
    
- bool - false
    
- char - ‘\0’
    
- string - “”
    

  
  
  

IMPLICIT CONVERSION

  

- Is the usual need to convert data to type X for type Y.
    
- There are two ways to convert it, the implicit and the explicit.
    
- The implicit is the conversion that:
    

- Can be executed only with data passing
    
- Have a compatible type.
    

  
  

|   |   |
|---|---|
||float value = 25.8f;<br><br>int other = 25;<br><br>  <br><br>value = other; // Implicit conversion|

  

- This conversion above is allowed because a real number (float) can receive a whole number (int).
    
- Although, the opposite shouldn’t allowed.
    

- A whole number doesn’t have a dot.
    
- So it can’t receive a real number (float).
    

- The conversion is only allowed if
    

- The data type is compatible
    
- The weight of data is compatible.
    

- In the case of the number, the precision may be altered.
    
- Every adversarial situation results in error.
    

  
  

- sbyte
    

- short, int, long, float, double, decimal.
    

- byte
    

- short, ushort, int, uint, long, ulong, float, double, decimal.
    

- short
    

- int, long, float, double, decimal.
    

- int
    

- long, float, double, decimal.
    

- uint
    

- long, ulong, float, double, decimal
    

- long
    

- float, double, decimal.
    

- ulong
    

- float, double, decimal.
    

- char
    

- ushort, int, uint, long, ulong, float, double, decimal.
    

  

EXPLICIT CONVERSION

  

- Is used when the types aren’t compatible with each other.
    
- It uses the type between parenthesis.
    
- Follow the same rules as implicit conversion.
    

  

|   |   |
|---|---|
||int number = 100;<br><br>uint unsignedNumber = (uint)number; // Explicit conversion|

  
  

PARSE

  

- Is a method present in all primitive types.
    
- Is Used to convert a character or string into any other type.
    
- If there is some incompatibility, it generates an error.
    

  

|   |   |
|---|---|
||var stringNumber = “100”;<br><br>int number = int.Parse(stringNumber);|

  
  

CONVERT

  

- It is like the parse.
    
- But, convert allows the conversion of some types of value.
    

- Not only string.
    

- We should inform the type at the conversion call.
    

  
  

|   |   |
|---|---|
||var stringNumber = “100”;<br><br>int number = Convert.ToInt32(stringNumber);|

  
  

ARITHMETIC OPERATORS

  

- Addition => +
    
- Subtraction => -
    
- Multiplication => *
    
- Division => /
    

  

- Multiplication and Division are executed first.
    
- If we want to execute the operation in another sequence, we must use parentheses.
    
- It works with short, int, float, double, and decimal.
    
- If the var is a whole number (int), the real numbers' value is rounding.
    

- 4.4 => 5
    

  
  

|   |   |
|---|---|
||int addition = 25 + 22; // 47<br><br>int subtraction = 25 - 22; // 3<br><br>int multiplication = 25 * 22; // 550<br><br>int division = 25 / 22; // 4 - It was rounding.|

  

- Parentheses are used to redefine the execution sequence.
    

  

|   |   |
|---|---|
||int x = 2 + 2 * 2; // 6<br><br>int x = (2 + 2) * 2; // 8 - Execute the sum first.|

  
  
  
  
  

ASSIGNMENT OPERATORS

  

- The equal sign (=) is used to assign a value to a variable.
    
- Although, we can use equal signs with an arithmetic operator
    
- x += 5 is the same as x = x + 5.
    

  

|   |   |
|---|---|
||int x = 0; // Assignment<br><br>x += 5; // x = x + 5<br><br>x -= 1; // x = x - 1<br><br>x *= 10; // x = x * 10<br><br>x /= 2; // x = x / 2|

  
  

COMPARISON OPERATORS

  

- We can compare all types of data.
    

- Numbers, strings, bytes.
    

- The comparison ALWAYS returns true or false.
    

  

- Equal to
    

- ==
    

- Not equal
    

- !=
    

- Greater than
    

- >
    

- Less than
    

- <
    

- Greater than or equal to
    

- >=
    

- Less than or equal to
    

- <=
    

  

|   |   |
|---|---|
||int x = 25; // Assignment<br><br>x == 0; // False<br><br>x != 0; // True<br><br>x > 0; // True<br><br>x < 0; // False<br><br>x <= 0; // False<br><br>x >= 0; // True|

  

LOGICAL OPERATORS

  

- Is used in conditionals operations.
    
- It ALWAYS returns true or false.
    
- and.
    

- Must comply with all conditions to return true.
    
- &&
    

- or.
    

- If one condition is complied with, it returns true.
    
- ||
    

- not
    

- !
    

  
  

CONDITIONAL OPERATORS

  

- If
    

- Is used to decisions.
    
- Use logical operators.
    

- Else
    

- If complement.
    
- Used when the conditional doesn’t comply with.
    
- We can use:
    

- else if (condition).
    
- Doesn’t have a limit (but be careful).
    

- Use only else to execute something when the conditional doesn’t comply with.
    

  
  

|   |   |
|---|---|
||if(conditional) { // When it’s true.<br><br>  ...<br><br>}<br><br>  <br><br>if(conditional)  // When it’s true.<br><br>  ...           // When the if has only one line, it doesn’t<br><br>                    need brackets.|

  

|   |   |
|---|---|
||if(conditional) { // When it’s true.<br><br>  ...<br><br>} else { // When it’s false.<br><br>  ...<br><br>}<br><br>  <br><br>if(conditional)  // When it’s true.<br><br>  ...            // When the if has only one line, it doesn’t<br><br>                    need brackets.<br><br>else {          // When it’s false.<br><br>  ...|

  
  

CONDITIONAL STRUCTURE: SWITCH

  

- Is used when is needed take many decisions.
    
- Is executed in cascade.
    
- Is needed to break the execution with break command.
    
- It has a default execution called default.
    

  

|   |   |
|---|---|
||int value = 1;<br><br>switch (value)<br><br>{<br><br>  case 1: Console.WriteLine(“1”); break;<br><br>  case 2: Console.WriteLine(“2”); break;<br><br>  case 3: Console.WriteLine(“3”); break;<br><br>  default: Console.WriteLine(“4”); break;<br><br>}|

  
  

FOR LOOPS

  

- For each item in a value…
    
- It executes a certain action once and again.
    
- Defined as for word.
    
- Needs 3 parameters:
    

- Counter;
    
- Condition;
    
- Increment.
    

- for (var i = 0; i <= 5; i ++)
    

  
  

|   |   |
|---|---|
||//0 to 5 count.<br><br>for (var i = 0; i <= 5; i++ )<br><br>  Console.WriteLine(i);<br><br>  <br><br>/*Console print:<br><br>0<br><br>1<br><br>2<br><br>3<br><br>4<br><br>5<br><br>*/|

  
  

WHILE LOOPS

  

- While a condition is true…
    
- Defined as while word.
    
- Demand only one condition.
    
- It checks the condition BEFORE to execute.
    
- If the condition is false, it doesn’t execute.
    

  
  

|   |   |
|---|---|
||var value = 0;<br><br>  <br><br>//0 to 5 count.<br><br>while (value <= 5 )<br><br>{<br><br>  Console.WriteLine(value);<br><br>  value++;<br><br>}<br><br>  <br><br>/*Console print:<br><br>0<br><br>1<br><br>2<br><br>3<br><br>4<br><br>5<br><br>*/|

  
  
  
  
  
  

DO LOOPS

  

- Do a action while…
    
- Defined as do/while word.
    
- Demand only one condition at while.
    
- It checks the condition AFTER to execute.
    

  
  

|   |   |
|---|---|
||var value = 0;<br><br>  <br><br>do<br><br>{<br><br>  Console.WriteLine(“Test”);<br><br>  value++;<br><br>} while (value < 5)<br><br>  <br><br>/*Console print:<br><br>Test<br><br>Test<br><br>Test<br><br>Test<br><br>Test<br><br>*/|

  
  

FUNCTIONS OR METHODS

  

- We can group our program in functions.
    
- Also known as methods
    
- The main is an example of a method.
    
- Has a return, a name, and parameters.
    
- Its composition is “camada de assinatura”(I don’t know what is it in English).
    
- Starts always with the uppercase first letter.
    

  

|   |   |
|---|---|
||static void Main(string[] args)<br><br>{<br><br>  //Method call<br><br>  MyMethod(“C# is cool!”);<br><br>}<br><br>  <br><br>//Method definition<br><br>static void MyMethod(string parameter)<br><br>{<br><br>  Console.WriteLine(parameter);<br><br>}|

  
  

VALUE TYPE & REFERENCE TYPES(IMPORTANT)

  

- The memory is divided into two parts, Heap e Stack.
    
- Heap storage data.
    
- Stack storage data references.
    
- At .NET all types are
    

- Reference Types
    
- Value Types
    

  
  

- Value types storage data.
    
- Are stored in a memory local called Stack.
    
- When a value is stored, the memory is allocated.
    
- This space stores the data created.
    
- The variable accesses this data directly.
    
- If to assign a value type variable to another variable
    

- The value is COPIED.
    
- The both are independents.
    

- Built-in, Structures and Enums are always value types.
    
- Garbage Collector doesn’t access the Stack.
    
- The Garbage Collector inspects the Heap memory and if something isn’t used, the garbage collector deletes this.
    

  
  

|   |   |
|---|---|
||int x = 25;<br><br>int y = x; //Y is a copy of x, not only a reference.<br><br>Console.WriteLine(x); // 25<br><br>Console.WriteLine(y); // 25<br><br>x = 32; //Only x is changed.<br><br>Console.WriteLine(x); // 32<br><br>Console.WriteLine(y); // 25|

  
  

- Reference types store the address from the object that contains the data.
    
- Doesn’t store the data itself.
    
- Are stored in a memory local called Heap.
    
- To assign a variable
    

- Create a reference
    
- Point to the same information/target.
    
- Doesn’t independent.
    

- When it is not used is reserved to delete.
    
- Garbage Collector removes all of this.
    
- Classes, Objects, Arrays…
    

  
  

STRUCTS

  

- Is a structured type of data.
    
- Only the structure, the skeleton.
    
- Value type.
    
- Store only other types of data.
    
- Defined as the structure word.
    
- Composed by properties and methods.
    
- The name is always with uppercase.
    

- The same for the properties and methods.
    

- Created by the new word.
    

- In this moment we have the values.
    

  
  
  
  
  
  
  
  

- The struct anatomy is usually like this:
    

  

|   |   |
|---|---|
||structure StructureName<br><br>{<br><br>  //Properties<br><br>  public int Id;<br><br>  //Methods<br><br>}|

  
  
  
  

|   |   |
|---|---|
||structure StructureName<br><br>{<br><br>  public int Id;<br><br>  public float Price;<br><br>  <br><br>  public float PriceInDolar(float dollar)<br><br>  {<br><br>    return Price * dollar;<br><br>  }<br><br>}|

  
  

- To create a structure:
    

  

|   |   |
|---|---|
||//Create a structure<br><br>var product = new StructureName();<br><br>product.Id = 1;<br><br>product.Price = 5.65;|

  
  

- Constructor method is a method with the same name as the structure.
    

  

|   |   |
|---|---|
||structure StructureName<br><br>{<br><br>  public StructureName(int id, string title, float price)<br><br>  {<br><br>    Id = id;<br><br>    Title = title;<br><br>    Price = price;<br><br>  }<br><br>}|

  
  

- This make it easier to create structures.
    

  

|   |   |
|---|---|
||var product = new StructureName(1, “Mouse Gamer”, 65.50);|

  
  
  
  
  
  
  
  
  
  
  

ENUMS

  

- Used to provide a better code vizualization.
    
- Replace the use of integers(int).
    
- Used in short lists.
    
- Used in fixed data.
    

- Hard Coded.
    

- Always in uppercase.
    

- Start with the E letter.
    

  

- Enum anatomy:
    

  

|   |   |
|---|---|
||enum EMaritalStatus<br><br>{<br><br>  Single = 1,<br><br>  Married = 2,<br><br>  Divorced = 3,<br><br>}|

  
  

- The use of an Enum is like this:
    

  

|   |   |
|---|---|
||struct Customer<br><br>{<br><br>  public string Nome;<br><br>  public EMaritalStatus MaritalStatus;<br><br>}|

  
  

GUIDS

  

- In databases we use so much ID’s to identify something. In C# we can use the GUID to facilitate this.
    
- Example:
    

  

|   |   |
|---|---|
||var id = Guid.NewGuid();|

  
  

STRINGS INTERPOLATION

  

- We can interpolate/mix strings with other variables.
    
- Example:
    

  

|   |   |
|---|---|
||var price = 10.2<br><br>var text = $“The product price is {price}.”|

  
  
  
  
  
  
  
  

STRING COMPARE

  

- We can compare one string to another object.
    
- Example:
    

  

|   |   |
|---|---|
||var text = “Testing”;<br><br>Console.WriteLine(text.CompareTo(“Testing”));<br><br>  <br><br>// If returns 0, It means the comparison is good.<br><br>//If returns 1 or more, the comparison is bad.|

  

- Another method to compare strings is the Contains method.
    
- Example:
    

  

|   |   |
|---|---|
||var text = “This text is a test.”;<br><br>Console.WriteLine(text.Contains(“test”));<br><br>  <br><br>// If returns true, It means the comparison is good.<br><br>//If returns false, the comparison is bad.<br><br>//It searches the word required into the string.|

  

- In both cases, we can ignore the case sensitive to compare.
    

  

|   |   |
|---|---|
||Console.WriteLine(text.Contains(“test”, StringComparison.OrdinalIgnoreCase));|

  
  
  

START WITH / END WITH

  

- The StartsWith analyze if the text starts with the string we put into this.
    
- The EndsWith analyze if the text ends with the string we put into this.
    

  

|   |   |
|---|---|
||var text = “This text is a test.”;<br><br>Console.WriteLine(text.StartWith(“This”));<br><br>Console.WriteLine(text.StartWith(“test”));<br><br>  <br><br>// If returns true, It means the comparison is good.<br><br>//If returns false, the comparison is bad.<br><br>//It searches the word required into the string.|

  
  

EQUALS

  

- Equal is a method that exists in some objects at dotnet.
    
- This compares if the required value is exactly the same as the var analyzed.
    

  

|   |   |
|---|---|
||var text = “This text is a test.”;<br><br>Console.WriteLine(text.Equals(“This text is a test.”));<br><br>  <br><br>// If returns true, It means the comparison is good.<br><br>//If returns false, the comparison is bad.<br><br>//It works in other objects/built-in types.|

  
  
  
  
  
  
  
  
  
  
  
  
  

INDEX

  

- The Index method indicates the position in a list. 
    
- In the case of the strings, it indicates the word position. 
    

- Strings are char lists.
    

- When the value is repeated, we can use the LastIndexOf
    

  

|   |   |
|---|---|
||var text = “This text is a test.”;<br><br>Console.WriteLine(text.Indexof(“a”));<br><br>Console.WriteLine(text.LastIndexof(“t”));<br><br>  <br><br>// It returns the position.<br><br>//In the IndexOf case the 8th position.<br><br>//In the LastIndexOf case the 18th position.|

  
  

ADDITIONAL METHODS

  

- The ToUpper converts all text to uppercase. 
    
- The ToLower converts all text to lowercase. 
    

  

|   |   |
|---|---|
||var text = “This text is a test.”;<br><br>Console.WriteLine(text.ToUpper());<br><br>Console.WriteLine(text.ToLower());<br><br>  <br><br>// ToUpper = THIS TEXT IS A TEST.<br><br>//ToLower = this text is a test.|

  
  

- The Insert method inserts a value into a list.
    
- In the case of strings, insert words, phrases, or letters.
    
- We need to inform the position that the value will be inserted and after the coma, the value.
    

  

|   |   |
|---|---|
||var text = “This text is a test.”;<br><br>Console.WriteLine(text.Insert(9, “HERE ”));<br><br>  <br><br>// RETURN = This text HERE is a test.|

  

- Also, the Remove method removes a value.
    
- We need to inform what the initial position is and how much you want advance to remove.
    

  

|   |   |
|---|---|
||var text = “This text is a test.”;<br><br>Console.WriteLine(text.Remove(9,5));<br><br>  <br><br>// RETURN = This text is a test.|

  

- The Length property shows the length of a list.
    

  
  
  
  
  
  

MANIPULATING STRINGS

  

- The Replace method replaces all values you want in a list.
    

  

|   |   |
|---|---|
||var text = “This text is a test.”;<br><br>Console.WriteLine(text.Replace(“This”, “It”));<br><br>  <br><br>// RETURN = It text is a test.|

  

- The Split method splits the list based on informed value.
    

  

|   |   |
|---|---|
||var text = “This text is a test.”;<br><br>Console.WriteLine(text.Split(“ ”));<br><br>  <br><br>/* RETURN = This<br><br>            text<br><br>            is<br><br>            a<br><br>            test.<br><br>*/|

  

- The Substring method catches the characters based on position.
    
- We need to inform the char position and how many steps we deserve.
    

  

|   |   |
|---|---|
||var text = “This text is a test.”;<br><br>Console.WriteLine(text.Substring(5,4));<br><br>  <br><br>// RETURN = text|

  
  

STRING BUILDER

  

- Is recommended to use string builder when dealing with long texts with breakpoints.
    
- Is required to import System.Text to use StringBuilder.
    
- Using the StringBuilder, we can add text using a huge less memory allocation.
    

- To add text to a var with StringBuilder use .Append.
    

- To use the string with StringBuilder is needed to convert it into a string using .ToString method.
    

  

|   |   |
|---|---|
||using System.Text;<br><br>  <br><br>var text = new StringBuilder();<br><br>text.Append(“My add text”)<br><br>  <br><br>Console.WriteLine(text.ToString());|

  
  
  
  
  
  
  
  

DATETIME

  

- .NET has a type called DateTime.
    
- It is a struct type.
    
- You need to specify the date and time.
    

- If you don’t specify, it is initiated with the default date and time.
    

- To use the current date and time, use DateTime.Now
    

  

|   |   |
|---|---|
||var date = DateTime.Now;|

  

- To use custom for DateTime, use ToString, and pass the format.
    

- If have a doubt, look at the formats in [Microsoft C# documentation](https://learn.microsoft.com/en-us/dotnet/standard/base-types/standard-date-and-time-format-strings).
    

  

|   |   |
|---|---|
||var date = DateTime.Now;<br><br>var customFormat = date.ToString(“dd/MM/yyyy”);<br><br>  <br><br>Console.WriteLine(customFormat);<br><br>  <br><br>// RETURN = 29/09/2023(This is today when I wrote.)|

  

- To add days at the date, use .AddDays.
    
- To add Months at the date, use .AddMonths.
    
- To add Years at the date, use .AddYears.
    

  

|   |   |
|---|---|
||var date = DateTime.Now;<br><br>var OneMoreDay = date.AddDays(5);<br><br>var OneMoreMonth = date.AddMonths(3);<br><br>var OneMoreYear = date.AddYears(2);<br><br>  <br><br>Console.WriteLine(OneMoreDay);<br><br>Console.WriteLine(OneMoreMonth);<br><br>Console.WriteLine(OneMoreYear);<br><br>  <br><br>/* RETURN = 04<br><br>            12<br><br>            2025<br><br>*/|

  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  

- The CultureInfo class provides information about a specific culture (called a locale for unmanaged code development).
    

  

|   |   |
|---|---|
||using System.Globalization;<br><br>  <br><br>var ptPT = new CultureInfo(“pt-PT”);<br><br>var ptBR = new CultureInfo(“pt-BR”);<br><br>var enUS = new CultureInfo(“en-US”);<br><br>var deDE = new CultureInfo(“de-DE”);<br><br>  <br><br>Console.WriteLine(DateTime.Now.ToString(“D”, ptPT));<br><br>Console.WriteLine(DateTime.Now.ToString(“D”, ptBR));<br><br>Console.WriteLine(DateTime.Now.ToString(“D”, enUS));<br><br>Console.WriteLine(DateTime.Now.ToString(“D”, deDE));<br><br>  <br><br>/* RETURN = sexta-feira, 29 de setembro de 2023<br><br>            sexta-feira, 29 de setembro de 2023<br><br>            Friday, September 29, 2023<br><br>            Freitag, 29. September 2023<br><br>*/|

  

- CultureInfo.CurrentCulture Show the Culture of your system. 
    

  
  

- To get a global date and time use DateTime.UtcNow.
    

- To convert in the system date
    

- DateTime.UtcNow.ToLocalTime
    

- To convert in some timezone
    

- TimeZoneInfo.ConverTimeFromUtc(utcDateTime, timezoneChoosed)
    

  
  

- The TimeSpan is used to define a precise time.
    

  

|   |   |
|---|---|
||var hms= new TimeSpan(5, 12, 8);<br><br>Console.WriteLine(hms);<br><br>  <br><br>/* RETURN = 05: 12: 08<br><br>*/|

  
  

OTHERS DATES FUNCTIONS

  

- DateTime.DaysInMonth(year, month) shows how many days are in a month
    
- To see if the day is on the weekend we can use this bool:
    

- static bool IsWeekend(DayOfWeek today)
    

{

  return today == DayOfWeek.Saturday || today == DayOfWeek.Sunday;

}

- The DateTime.Now.DaylightSavingTime() Shows if is “horário de verão”.
    

  
  
  
  
  
  
  
  
  
  

CURRENCY

  

- Usually the decimal type is used to deal with money values.
    

- Remember when using decimal  is required add an m in the value final.
    

- Example: var money = 10.50m;
    

- The CultureInfo is used to inform the currency.
    

- The “C” is used to inform you want to show the currency.
    

- money.ToString(“C”, CultureInfo.CreateSpecificCulture(“pt-BR”))
    

- Besides the “C”, numbers types have other formats.
    

- “B” - Binary;
    
- “C” - Currency;
    
- “D” - Decimal;
    
- “E” - Exponential;
    
- “F” - Fixed-point;
    
- “G” - General;
    
- “N” - Number;
    
- “P” - Percent;
    
- “R” - Round-trip;
    
- “X” - Hexadecimal.
    

  

MATH

- Is a .Net method for math operations like Square root, Cosine, and others.
    
- The Math.Round(var), round the var, cutting the numbers after a point.
    
- The Math.Celling(var), round up the var.
    
- The Math.Floor(var), round down the var.
    

  
  

ARRAYS

  

- Is declared with new type[length] {values,  comma division}.
    

- var myArray = new int[5] { 1, 2, 3, 4, 5 };
    

- To put values in the array positions use myArray[position] = value.
    

- myArray[0] = 35;
    

- To clone Arrays, use array clone like this: (type[]) myArray.Clone().
    

- var clonedArray = (int[]) myArray.Clone;
    

  

TRAVERSING ARRAY

  

- With Array.Length we can see the array length.
    
- So we can use a for loop to traverse an array.
    

- for (var i = 0; i < myArray.Length; i++)
    

  

FOR EACH

  

- Also we can use foreach to traverse an array.
    

- foreach(var i in myArray)
    

  
  
  
  
  
  
  
  

EXCEPTIONS

  

- Exceptions are the errors in code.
    

  

TRY/CATCH

- try
    

{

  //Your Code to try.

}

catch

{

  //Some code like bellow.

  Console.WriteLine(Ops, something is wrong!);

}

  

- We can put some properties in the catch to look at errors.
    

- catch( Exception ex)
    
- When we look ex, we can see and deal with errors.
    

- Examples: 
    
- ex.InnerException - Describe the error.
    
- ex.Message - Explain the error.
    

  

DISPARAR EXCEPTIONS

  

- We can disparar exceptions when some in our code don’t run in the order we want.
    

- To string that shouldn’t be null.
    
- if (string.IsNullOrEmpty(text))
    

throw new Exception (“The text should not be null or empty.”)

  

CUSTOM EXCEPTIONS

  

- public class MyException : Exception
    

{

  //It needs

  public MyException(DateTime date)

  {

    WhenItsHappens = date;

  }

  //Custom parameter exception

  public DateTime WhenItsHappens { get; set }

}

  

FINALLY

  

- Is used after the catch to be executed always in the end.
    

- finally
    

{

  //Your code.

}

**