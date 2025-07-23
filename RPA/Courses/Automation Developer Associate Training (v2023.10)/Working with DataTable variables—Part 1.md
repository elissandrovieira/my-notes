## 🗺️Overview

DataTable variables store data structured in a tabular form. 

In other words, information is organized into rows and columns. This variable type is similar to a spreadsheet.

As a key difference, Data Table cells are identified through the Column Name or Column Index and by the Row Index, both starting from zero. A spreadsheet cell is identified by a column letter and a row number starting at one. 

We can use the **Join Data Tables** activity to combine rows from two tables by using values common to each other, according to a Join rule. We can convert a data table to a string using the **Output Data Table** activity.
## 🤔What activities can we use to work with DataTable variables?

UiPath Studio offers a broad range of activities that can be used to work with DataTable variables. Let's learn more about them!

- Add Data Column
	Adds a column to an existing DataTable variable. The input data can be of DataColumn type or the column can be added empty, by specifying the data type and configuring the options (allowing null values, requesting unique values, auto-incrementing, default value and maximum length). 
	
- Add Data Row
	Adds a new row to an existing DataTable variable. The input data can be of DataRow type or can be entered as an Array Row, by matching each object with the data type of each column. 
	
- Build Data Table
	Is used to create a DataTable using a dedicated window. This activity allows the customization of number of columns and type of data for each column. 
	
- Clear Data Table
	Clears all the data in an existing DataTable variable.
	
- Filter Data Table
	Enables you to filter a DataTable variable by specifying conditions in the Filter Wizard window. The activity can keep or delete rows or columns according to the logical conditions that are specified in the wizard. The body of the activity contains a Filter Wizard button so that you can access the wizard and customize your settings at any time. 
	
- For Each Row in Data Table
	Is used to perform a certain activity for each row of a DataTable (similar to a For Each loop).
	
- Generate Data Table From Text
	Can be used to create a DataTable from structured text, by letting the user indicate the row and column separators.
	
- Get Row Item
	Retrieves a value from a row in a DataTable according to a specified column.
	
- Join Data Tables
	Combines rows from two tables by using values common to each other using the **Join Wizard**, according to a Join rule that answers the question "What to do with the data that doesn't match?". 
	
	It's one of the most useful activities in business scenarios, where working with more than one Data Table is very common.
	
- Lookup Data Table
	
	This activity emulates the behaviour of the VLOOKUP Excel formula. It enables you to search for a provided value in a specified DataTable and returns the **RowIndex** at which it was found. If the provided value isn't found, then the returned **RowIndex** is -1. 
	
	  
	This activity can also help you return the value found in the cell that has the row coordinates specified in the **RowIndex** property and the column coordinates specified in the **Target Column** property category. 
	
- Merge Data Table
	
	Merges the Destination with the Source, indicating whether to preserve changes and how to handle missing schema in the Source.  The operation is more simple than the Join Data Type activity, as it has 4 predefined actions to perform over the missing schema.
	
- Output Data Table
	
	Writes a DataTable to a string using the CSV format.
	
- Remove Data Column
	
	Removes a certain column from a specified DataTable. The input may consist of the column index, column name or a Data Column variable.
	
- Remove Data Row
	
	Removes a row from a specified DataTable. The input may consist of the row index or a Data Row variable.
	
- Remove Duplicate Rows
	
	Removes the duplicate rows from a specified DataTable variable, keeping only the first occurrence.
	
- Sort Data Table
	
	Can sort a DataTable ascending or descending based on the values in a specific column.
	
- Update Row Item
	
	Assigns a specified value to the indicated column of a DataTable row.
