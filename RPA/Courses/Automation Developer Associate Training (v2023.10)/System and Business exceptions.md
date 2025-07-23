## 🗺️Overview

Errors are events that occur in a program and can't be handled normally.

On the other hand, exceptions are events that are recognized, categorized, and handled by the program. 

| ERRORS                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               | EXCEPTIONS                                                                                                                                                                                                                                                                                                                                                                                                                      |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Errors** are events that a particular program can’t normally deal with. There are different types of errors, based on what's causing them—for example: <br><br>- **Syntax errors**, where the compiler/interpreter can't parse the written code into meaningful computer instructions.<br>- **User errors**, where the software determines that the user’s input isn't acceptable for some reason.<br>- **Programming errors**, where the program contains no syntax errors but doesn't produce the expected results. These types of errors are often called bugs. | **Exceptions** are events that are recognized (caught) by the program, categorized, and handled. More specifically, there is a routine configured by the developer that is activated when an exception is caught. Sometimes, the handling mechanism can be simply stopping the execution.<br><br>  <br><br>Some of the exceptions are linked to the systems used, while others are linked to the logic of the business process. |

___
## 💻System exceptions 

The unexpected exceptions are the one known as System Exceptions (SE). They're also called Application Exceptions (AE), but the underlying concept remains the same. They belong to the .NET framework and are categorized under the System.Exception class. Proper handling should be in place for these kinds of exceptions and they can cause the process to fail.

The below list encompasses the most common exceptions that you can encounter in projects developed with Studio. They are derived from System.Exception as mentioned already, so using this generic type in a TryCatch, for example, will catch all types of errors.

1. **NullReferenceException**—Occurs when using a variable with no set value (not initialized).
    
2. **IndexOutOfRangeException**—Occurs when the index of an object is out of the limits of the collection.
    
3. **ArgumentException**—Is thrown when a method is invoked and at least one of the passed arguments doesn't meet the parameter specification of the called method.
    
4. **SelectorNotFoundException**—Is thrown when the robot is unable to find the specified selector for an activity in the target app within the Timeout period. As you know, the timeout property specifies the amount of time, in seconds, that the system will wait for an operation to finish before generating an error.
    
5. **ImageOperationException**—Occurs when an image isn't found within the Timeout period.
    
6. **TextNotFoundException**—Occurs when the indicated text isn't found within the Timeout period.
    
7. **ApplicationException**—Describes an error rooted in a technical issue, such as an application that isn't responding.

![[Pasted image 20250504151426.png]]

---

## 💼Business exceptions

On the other hand, the expected exceptions are the ones referred to as Business Rule Exceptions (BRE). 

A business exception mainly refers to information used in an automated process; either it may be incomplete or incorrect from a business perspective. When business exceptions occur, robots stop the process, and it requires human intervention to address a thrown exception.

Some of the examples of business exceptions are: certain pieces of data which the automation project depends on are incomplete, missing, outside set boundaries (like trying to extract more from the ATM than its daily limit), or don't pass other data validation criteria.

The message associated with a business rule exception should provide meaningful information for the process. For example, if a business rule states that only purchase orders (POs) with a value greater than USD1000 should be processed, the code would include an If statement to check the value. If the value is less than or equal to USD 1000, a Business Rule Exception (BRE) is thrown with a message like "The PO <id of PO> value is less or equal than USD 1000. The transaction is not processed."

BREs aren't automatically generated as system exceptions. They must be defined by a developer by using the Throw Activity and handled inside a TryCatch.