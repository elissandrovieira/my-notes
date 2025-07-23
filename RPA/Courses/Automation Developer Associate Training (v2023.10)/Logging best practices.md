## 👍Effective logging practices

When diagnosing a process in production, you'll find that oftentimes, the default exception log messages are helpful, but not enough to provide a full picture of why it's failing. User-defined logs are the breadcrumbs you can use to track your robot's progress through the process and get a better view of the execution. 

On the other hand, **over-logging** can increase the load on Orchestrator, slow your process down, and make it hard to diagnose an issue because of the sheer volume of log entries.

The solution is to define the right log messages at strategic points in your project. The recommendations below cover some healthy uses for identifying events that could lead to issues. 

1. Log message activities should ideally be used in the following scenarios: 
	
	- Each time an exception is caught in a Catch block (**Log level = Error**). 
	
	- Each time a Business Rule Exception is thrown (**Log Level = Error**).
	
	- When data is read from external sources. For example, log a message at Information level when an Excel file is read (Log Level = Information). 
	
	- In Parallel or Pick activities, log messages on every branch, to trace the branch is taken (**Log Level = Information**). 
	
	- In If/Flowchart Decision/Switch/Flow Switch activities. 
	    
	    **Note:** There should be no more than two (maximum three) nested IF statements so it depends from workflow to workflow if you should add or not log message activities.

2. When you invoke a workflow use the two properties Log Entry and Log Exit (Log level = Information). These let you specify if you want to log entry into/ exit from an invoked workflow. This is particularly useful for debugging without adding lots of Log Message activities. 

3. Write meaningful log messages: The message should be clear enough. 

4. Add context to your log message: Include values of meaningful variables in that context.