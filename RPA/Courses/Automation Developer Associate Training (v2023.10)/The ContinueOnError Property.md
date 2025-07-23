## 🗺️Overview

The "ContinueOnError" is a property that specifies if the execution of the activity should continue even when the activity throws an error.

| ![[Pasted image 20250504152749.png]] | This field only supports Boolean values (True, False). The default value is False. As a result, if the field is blank and an error is thrown, the execution of the project stops. If the value is set to True, the execution of the project continues regardless of any error. |
| ------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |

When the "ContinueOnError" property is set to True on an activity that has a scope (such as Attach Window, Attach Browser, or Use Application Browser), any errors thrown by the activities within the scope's DO container will also be ignored. This means that even if an error occurs within the scope, the execution will continue without stopping.

However, it's important to note that setting the "ContinueOnError" property to True isn't recommended in all situations. It should be used with caution. There are specific cases where it can be useful, such as 

- When performing data scraping and the selector for the "Next" button is not found on the last page. In such scenarios, setting "ContinueOnError" to True prevents the activity from throwing an error and allows the workflow to continue executing.

- Similarly, when the focus is solely on the execution of the activity and capturing the error isn't necessary or relevant, setting "ContinueOnError" to True can be appropriate.

>[!WARNING]
>**If an activity is included in Try Catch, in the Try section, and the value of the ContinueOnError property is True, no error is caught when the project is executed.**

