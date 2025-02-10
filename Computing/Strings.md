# C# 
### Strings

The key thing to remember about [[Csharp]] strings is that they are immutable objects representing text as a sequence of Unicode characters (letters, digits, punctuation, etc.). Double quotes are used to define a `string` instance:

```csharp
string fruit = "Apple";
```

Manipulating a string can be done by calling one of its [methods](https://docs.microsoft.com/en-us/dotnet/api/system.string) or [properties](https://docs.microsoft.com/en-us/dotnet/api/system.string). As string values can never change after having been defined, all string manipulation methods will return a new string.

A string is delimited by double quote (`"`) characters. Some special characters need [escaping](https://devblogs.microsoft.com/csharpfaq/what-character-escape-sequences-are-available/) using the backslash (`\`) character. Strings can also be prefixed with the at (`@`) symbol, which makes it a [verbatim string](https://csharp.net-tutorials.com/data-types/strings/#aelm5298) that will ignore any escaped characters.

```csharp
string escaped = "c:\\test.txt";
string verbatim = @"c:\test.txt";
escaped == verbatim;
// => true
```

#### Methods

Strings are manipulated by calling the string's [built-in methods](https://docs.microsoft.com/en-us/dotnet/api/system.string). For example, to remove the whitespace from a string, you can use the [Trim method](https://docs.microsoft.com/en-us/dotnet/csharp/how-to/modify-string-contents#trim-white-space) like this:

```csharp
string name = " Jane "
name.Trim()
// => "Jane"
```

If you only need a part of a string, you can use the [`Substring()` method](https://docs.microsoft.com/en-us/dotnet/api/system.string.substring) to extract just that part:

```csharp
string sentence = "Frank chases the bus.";
string name = sentence.Substring(0, 5);
// => "Frank"
```

The [`IndexOf`() method](https://docs.microsoft.com/en-us/dotnet/api/system.string.indexof) can be used to find the index of the first occurence of a `string` within a `string`, returning `-1` if the specified value could not be found:

```csharp
"continuous-integration".IndexOf("integration")
// => 11

"continuous-integration".IndexOf("deployment")
// => -1
```
#### Concatenation

Finally, there are [many ways to concatenate a string](https://docs.microsoft.com/en-us/dotnet/csharp/how-to/concatenate-multiple-strings). The simplest one is by using the [`+` operator](https://csharp.net-tutorials.com/data-types/strings/#aelm5211).

```csharp
string name = "Jane";
"Hello " + name + "!";
// => "Hello Jane!"
```

For any string formatting more complex than simple concatenation, [string interpolation](https://docs.microsoft.com/en-us/dotnet/csharp/tutorials/string-interpolation) is preferred. To enable interpolation in a string, prefix it with the dollar (`$`) symbol.

```csharp
string name = "Jane";
$"Hello {name}!";
// => "Hello Jane!"
```

### Learn More
- [methods](https://docs.microsoft.com/en-us/dotnet/api/system.string?view=netcore-3.1#methods)
- [properties](https://docs.microsoft.com/en-us/dotnet/api/system.string?view=netcore-3.1#properties)
- [escaping](https://devblogs.microsoft.com/csharpfaq/what-character-escape-sequences-are-available/)
- [verbatim](https://csharp.net-tutorials.com/data-types/strings/#aelm5298)
- [concatenation](https://docs.microsoft.com/en-us/dotnet/csharp/how-to/concatenate-multiple-strings)
- [plus-operator](https://csharp.net-tutorials.com/data-types/strings/#aelm5211)
- [interpolation](https://docs.microsoft.com/en-us/dotnet/csharp/tutorials/string-interpolation)