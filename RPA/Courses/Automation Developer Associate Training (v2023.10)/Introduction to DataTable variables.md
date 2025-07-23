## 🤔What are DataTable variables?

DataTable is the type of variable that can store data as a simple spreadsheet with rows and columns. You can identify each piece of data based on its unique column and row coordinates. We can think of it as the memory representation of an Excel worksheet. 

In DataTable variables, individual cells can be identified using the column name/column index and the row index, both indexes starting from zero.

Variables of this type can be used for many purposes, including migrating specific data between databases, and extracting information from websites and storing it locally.

---

## 🤔What is the difference between a worksheet and a DataTable?

| ![[Pasted image 20250504155934.png]] | A DataTable is an in-memory representation of a single database table that has a collection of rows and columns.                         |
| ------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------- |
| ![[Pasted image 20250504160010.png]] | An Excel worksheet is a visual representation of data with different visualization options and extensive graphical user interface usage. |

---

## How are DataTables created?

The most common activities and methods to create DataTables are: 

- The 'Build Data Table' activity
	By using this activity, you choose the number of columns, the column name, and the data type of each of them.  Moreover, you can configure each column with specific options like allow null values, unique values, auto-increment (for numbers), default value and maximum length (for strings). 
	
- The 'Read Range' activity
	Reads the value of an Excel range and stores it in a DataTable variable. If the range isn't specified, the whole spreadsheet is read. If the range is specified as a cell, the whole spreadsheet starting from that cell is read. Can only be used in the Excel Application Scope or Use Excel File activities.
	
	**Note:** Workbook activities can be executed even if Microsoft Excel isn't installed on the machine and can only read/write data to and from the file.
	
- The 'Read Range Workbook' activity
	Reads the value of an Excel range and stores it in a DataTable variable. If the range isn't specified, the whole spreadsheet is read. If the range is specified as a cell, the whole spreadsheet starting from that cell is read.
	
- The 'Read CSV' activity
	This activity captures the content of a CSV file and stores it in a DataTable variable. Although not commonly used anymore, there are still legacy or internal-built applications that work with this kind of documents.
	
- Table Extraction
	Table Extraction, part of the **Modern** Experience in Studio, enables you to use the UI Automation activity package to automatically extract structured data from applications and save it as a DataTable object that can then be further used in your automation processes.
	
	This process can be done by using the **Table Extraction** Recorder in Studio, which can be accessed from the Ribbon if the **UI Automation** **v21.4 or above** pack is installed in your current project, and you have selected the Modern Experience.  
	
	The same wizard is also used when using a **Extract Table Data** activity in your workflow.
	
- The 'Data Scraping' action
	**Note:** To use this functionality, you must switch to the **Classic** _e_xperience in Studio. To enable or disable the modern experience for a project, in the **Project** panel, select **Project Settings**, then use the **Modern Design Experience** toggle from the **General** tab, and reload the project.  
	  
	This functionality of UiPath Studio enables you to extract structured data from your browser, application or document to a DataTable.
	
- The 'Generate Data Table From Text' activity
	Can be used to create a DataTable from structured text, by letting the user indicate the row and column separators.