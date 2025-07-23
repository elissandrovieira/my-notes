## 🚪Accessing logs

There are several places where you can access Robot Execution Logs: 

- In the **Output Panel** in UiPath Studio for the previous process execution from Studio. 

- In the ****%localappdata%\UiPath\Logs\<shortdate>_Execution.log** file** for all processes ran on the machine from UiPath Studio. Logs are generated at Trace level and above or Verbose level and above depending on whether the Verbose level is activated or not. 

- In the **%localappdata%\UiPath\Logs\<shortdate>_Execution.log** file for all processes ran on the machine from UiPath Assistant. The logs are generated at the level defined in UiPath Assistant and above. 

- In **Orchestrator**, in the Logs section when running processes while connected to Orchestrator. The logs are generated at the defined level and above.

---

## 🙆‍♂️The anatomy of a log entry

Let's now understand how log entries are structured. These entries can be very helpful when checking execution logs to analyze behavior or figure out what caused an exception. Logs are in the form of a **JSON**, pretty much just a **key-value pair (“field1:value1,” “field2:value2”)**. 

The default log fields are present in all logs: 

- **Message:** The log message. 

- **Level:** The log severity of the log message. 

- **Timestamp:** The exact date and time the action was performed.

- **FileName:** The name of the .xaml file being “executed".

- **JobId:** The key of the job running the process.

- **ProcessName:** The name of the process that triggered the logging.

- **ProcessVersion:** The version number of the process.

- **WindowsIdentity:** The name of the user that performed the action that was logged.

- **RobotName:** The name of the robot (as defined in Orchestrator).


Aside from default fields, logs can also contain type-specific fields and user-defined fields. 

- Type-specific fields are present depending on the log type, like totalExecutionTimeInSeconds and totalExecutionTime for Execution End. 

- User-defined fields are defined in Studio (by using the Add Log Fields Activity) and appear in all resulting logs after the activity is generated unless they are (programmatically) removed by the activity Remove Log Fields.