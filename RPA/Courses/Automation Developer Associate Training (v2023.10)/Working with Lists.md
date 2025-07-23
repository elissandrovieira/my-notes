## 🗺️Overview
Before we give a definition for list variables, we should know that list variables are collection type of variables. Meaning that they're part of the `System.Collections` namespace. Lists, queues, arrays, hash tables, and dictionaries are all part of the `System.Collections` namespace. 

List variables are exactly what they sound like. They can store numerous elements, like names, numbers, time coordinates, and many others.  
It's also possible to have a list within a list. Sounds pretty neat, right?

Lists provide specific methods of manipulation, such as:

- Adding and removing items.
- Searching for an element.
- Looping through the items (and performing certain actions on each).
- Sorting the objects.
- Extracting items and converting them to other data types.

---
## 🔍About lists and arrays

- ### What is a 'List' variable type?
	The `List<T>`  is a data structure part of the `System.Collections.Generic` namespace consisting of objects of the same data type. The '<**T**>' represents the **type** of elements in the list, for example strings or integers.
	
	Each object has a fixed position in the list, and thus it can be accessed by the specific index. Additionally, it provides methods for searching, sorting, and manipulating lists.

- ### What is an 'IList' variable type? 
	The **IList** is actually an Interface. In other words, it is a collection of objects that can be accessed individually by their specific **indexes**. As in the case of **List**, the '<**T**>' represents the **type** of elements in the list. The `IList<T>` generic interface is a descendant of the `ICollection<T>` generic interface and is the base interface of all generic lists. 
 
	Both **List** and **IList** type of variables can be initialized with `new list (of...)`. For example, if we have a List of IList of String elements type, looking like `List<IList<String>>`, we can write the following value in the Default value field to initialize it:  
	
		`new List (of IList(of String))`  
	  
	The same initialization value applies for the `IList<List<String>>` type of variable.

- ### What is the diference between lists and arrays?
	To begin with, both lists and arrays are collection types of variables.
	
	- The **array** variable enables you to store multiple values of the same type. UiPath Studio supports as many types of arrays as it does types of variables. This means that you can create an array of numbers, one of strings, one of Boolean values and so on.
	- While arrays are fixed-size structures for storing multiple objects, lists allow us to add, insert, and remove items.
	
	If you want to work with a collection that doesn’t have a fixed number of elements, you can use a list instead of an array.

---
### 🏗️ Think of it like this:

Imagine you're building with LEGO:

- `List(Of T)` is a **specific LEGO model kit** – it’s ready to use, with all the pieces and instructions.
    
- `IList(Of T)` is the **blueprint** (interface) – it just says: “You must have Add, Remove, and Index features” but doesn’t care how it’s built.
    

---

### 🧾 Now in VB.NET terms:

#### ✅ `List(Of T)` – a real, ready-to-use list

```vbnet 
Dim fruits As New List(Of String)
fruits.Add("apple")
fruits.Add("banana")
```

**You can:
- Add items
- Remove items
- Sort them
- Access by index

 💡 You’re using the real list with **all its features**.

---

#### 🔷 `IList(Of T)` – a more general type (an interface)

```vbnet
Dim fruits As IList(Of String) = New List(Of String)
fruits.Add("apple")`
```

It **still works** because `List(Of T)` implements `IList(Of T)`.

But now you’re telling VB.NET:

> “I only care that this thing acts like a list. I don’t care what kind of list it is.”

---

### 🤔 Why use `IList(Of T)` if `List(Of T)` has more features?

Because `IList(Of T)` gives you **flexibility**.

You can later change the list to something else (like a custom class or collection) **without changing your code**.

Example:

``` vbnet
' Code uses IList, so you can swap the implementation
Function GetFruits() As IList(Of String)
	Return New List(Of String) From {"apple", "banana"}
End Function`
```

Tomorrow you could return a different list-like class (e.g. a filtered list, or a read-only wrapper), and the rest of your code **won’t care**.

---

### ✅ Summary :

| Feature                  | Array                              | List(Of T)                          | IList(Of T)                                |
|--------------------------|-------------------------------------|-------------------------------------|---------------------------------------------|
| Is it concrete (usable)? | Yes                                 | Yes                                 | No (interface only)                         |
| Fixed size?              | Yes (cannot grow/shrink)            | No (dynamically resizable)          | Depends on the implementation               |
| Index access (`x(0)`)    | Yes                                 | Yes                                 | Yes                                          |
| Supports `.Add()`?       | No                                  | Yes                                 | Yes (if the implementation allows)          |
| Supports `.Sort()`?      | Yes (`Array.Sort(x)`)               | Yes (`x.Sort()`)                    | Depends on actual implementation            |
| Zero-based indexing?     | Yes                                 | Yes                                 | Yes                                          |
| Best used for...         | Performance-critical, fixed size    | General-purpose, flexible list      | Flexibility and abstraction                 |
| Easily replaceable?      | No                                  | No                                  | Yes                                          |

---

## How to initialize list variables

Prior to populating lists with values, the lists need to be initialized. In the video, **we explored two ways** to do this: 

1. The first way was to create a list type of variable. Then, we used a **Build Collection** activity to add items to the list and specify the list variable to hold the items. 
	![[Pasted image 20250502212858.png]]

2. The second way was to create a list type of variable, then add the items inside the Default value field. Then, initialize the list by typing new List of Type from the specified items.


To initialize a variable is to specify an initial value to assign to it. All variables are given an initial value when they are declared. However, this process is a bit different depending on whether the new variables are of the **value** or **reference** type.

- **Value type** - For numeric, Boolean, DateTime and other value types, the compiler will give them a valid value if we do not explicitly do so. For example, Ints initialize to zero by default, DateTimes initialize to DateTime.MinValue by default. In Studio, Strings are also assigned a blank default value, even though they are of the reference type.

- **Reference type** - Reference type variables, like Lists and Dictionaries, initialize to the object we provide. The compiler will not assign a value if we don't. This means we need to instantiate an object and assign it to the variable we've just declared.

To start using reference types like Lists and Dictionaries, we need to go through three steps:

1.  We **declare** a reference variable, for example a List of type **String**. We provide the name, select the type `System.Collections.Generic.List<T>` and select **String**.

2. We **initialize** an object to be assigned as the initial value for the variable. In our case, we want to start with a List of String object which does not contain values, so we use the expression **new List(of String)**.

3. We **assign** the object to the new variable (or initialize the variable) either by using the Default value in the Variables panel, or by using an **Assign** activity.

--- 
## The Invoke and String Conversion Method

- ### Invoke Method
	The Invoke Method activity is another way to implement a code which is outside of the standard built-in activities. You can use this activity to invoke a method of a class.
	
	The class does not need to be part of the workflow or use any of the workflow base classes. The Invoke Method calls a public method of a specified object or type.
	
	![[Pasted image 20250502213328.png]]


- ### String Conversion Method
	This method actually converts the first letter of every word in a string to uppercase and the following letters to lowercase.  
	  
	The arguments are as follows: the string to be converted, followed by the conversion settings, `VbStrConv.ProperCase`.
	
	  
	#### `StrConv(City,VbStrConv.ProperCase)`
	
	- **What works in Windows-Legacy projects:**  
	    `StrConv(City, VbStrConv.ProperCase)`
		`System.Globalization.CultureInfo.CurrentCulture.
		`TextInfo.ToTitleCase(City.ToLower)`
	
	- **What works in Windows projects:**  
	    `System.Globalization.CultureInfo.CurrentCulture.`
	    `TextInfo.ToTitleCase(City.ToLower)  
      
    The reason why the `StrConv(City, VbStrConv.ProperCase)` expression doesn't work in **Windows** projects is because **.Net Core** doesn't support Windows-1252 encoding out of the box.

---

> [!WARNING]
> **In UiPath Studio, you can manipulate lists using .NET methods or by using the ready-to-use collection activities.**

## Here are some collection-specific activities that we can use in Studio:

- ### Build Collection
	Creates a collection of items that have the same type as the first specified element. Learn more about it [here(opens in a new tab)](https://docs.uipath.com/activities/other/latest/user-guide/build-collection).

- ### Remove from Collection
	Removes the specified item from the specified collection. Learn more about it [here(opens in a new tab)](https://docs.uipath.com/activities/other/latest/user-guide/remove-from-collection).

- ### Exists in Collection
	Indicates whether a given item is present in a given collection by giving a Boolean output as the result. We can use this activity to check whether a list of clients contains a specific name. Learn more about it [here(opens in a new tab)](https://docs.uipath.com/activities/other/latest/user-guide/exists-in-collection).

- ## Append item to Collection
	Appends one or more items at the end of the specified collection. Learn more about it [here(opens in a new tab)](https://docs.uipath.com/activities/other/latest/user-guide/append-item-to-collection).

- ## Merge Collections
	Combines the elements of two collections in a new collection or an existing one. Learn more about it [here(opens in a new tab)](https://docs.uipath.com/activities/other/latest/user-guide/merge-collections).

- ### Filter Collection
	Filters a collection based on the specified conditions. Learn more about it [here(opens in a new tab)](https://docs.uipath.com/activities/other/latest/user-guide/filter-collection).

- ## Collection to Data Table
	Converts a specified collection to a DataTable. Learn more about it [here(opens in a new tab)](https://docs.uipath.com/activities/other/latest/user-guide/collection-to-data-table).