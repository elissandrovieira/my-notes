## 🗺️Overview

The Try Catch activity catches a specified exception type in a sequence or activity, and either displays an error notification or dismisses it and continues the execution.

As a mechanism, Try Catch runs the activities in the **Try block** and, if an error takes place, executes the activities in the **Catches block**. The **Finally block** is only executed when no exceptions are thrown or when an exception is caught and handled in the Catches block (without being re-thrown).

![[Pasted image 20250504152158.png]]

---

## ❌Don'ts

While the Try Catch activity can be helpful, it's important to avoid excessive usage. Catching an exception should only be done when there's a valid reason to do so. Typically, the Catch block is responsible for handling the exception and enabling error recovery. However, there are instances where an exception is caught performing certain actions, for the purpose of logging it, before being rethrown to higher levels.

Here are a few examples where the Try Catch activity shouldn't be used:

- When dealing with an Assign activity that involves filtering a DataTable. Instead of using it in a Try block, it's advisable to use an If statement. This Assign can throw an exception if the input DataTable (in_Datatable) is empty or if the Select operation doesn't return any results. By using an If statement, we can first check the necessary requirements before executing the Assign activity.

- In case of UI interaction, avoid placing Click or Type Into activities in Try Catch. Instead, use synchronization activities to check the availability of the target elements, such as: Element Exists, Find Element, Check App State etc.