## 🗺️Overview

In this lesson, we'll extract data from an Excel file, create a consolidated data table, generate email addresses, update the data table with the email addresses for each new hire, and write the data from the DataTable variable to an Excel spreadsheet.

### 1. **Project Setup**

- Two Excel files (HR and PM candidates) are placed in an **Input folder**.
    
- An **Output folder** is prepared for the final result.
    

---

### 🔹 2. **Reading Excel Files**

- `Read Range Workbook` activities are used to load data from:
    
    - **HR Candidates** → stored in `dt_HRCandidates`
        
    - **PM Candidates** → stored in `dt_ProductCandidates`
        

---

### 🔹 3. **Creating a Unified Schema**

- A `Build Data Table` activity defines the structure of the final `dt_Candidates`.
    
- Columns: First Name, Last Name, Department, Role, Status (all of type `Object`).
    

---

### 🔹 4. **Merging Data**

- `Merge Data Table` merges HR data into `dt_Candidates`.
    
- A second `Merge Data Table` adds PM data, ignoring the extra column.
    

---

### 🔹 5. **Filtering Hired Candidates**

- `Filter Data Table` keeps only rows where **Status = "Hired"**.
    

---

### 🔹 6. **Adding Email Column**

- `Add Data Column` adds a new column: **Business Email**.
    
- `AllowDBNull` is set to `True`.
    

---

### 🔹 7. **Generating Email Addresses**

- `For Each Row in Data Table` iterates through hired candidates.
    
- `Get Row Item` and `Assign` extract **First Name** and **Last Name**.
    
- Email is composed as: `firstname.lastname@acme.com`.
    
- `Update Row Item` stores the email in the "Business Email" column.
    

---

### 🔹 8. **Writing to Excel**

- `Write Range Workbook` exports `dt_Candidates` to:
    
    - **Output/New Hire Emails.xlsx**
        
    - Sheet: "Sheet One"
        
    - Includes headers
        

---

### 🔹 9. **Result**

- A new spreadsheet is created containing only hired candidates and their email addresses.