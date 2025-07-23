## 🗺️Overview

**In UiPath, selectors are like a robot's GPS—XML-based instructions that guide it to the exact UI element to interact with.** They’re built with tags and attributes, forming a path through the app’s interface. Get them right, and your automation hits the mark every time.
## 🔧Selectors

In UiPath Studio, **selectors** are **XML fragments** that serve as precise instructions telling the robot **which UI element to interact with**—whether it’s a button, input field, window, or menu. They are essential in **UI automation** for locating and interacting with elements in desktop and web applications.

### Key Characteristics

- ✅ **XML-Based**:  
    Selectors are written in **XML**, not JSON. They define a hierarchy of UI elements using attributes like `title`, `name`, `idx`, etc.

- 🛠️ **Automatically Generated**:  
    When you use activities like `Click`, `Type Into`, or `Get Text`, UiPath **automatically generates** the selector based on what you indicate on the screen. You can **edit or fine-tune** these selectors later in the **Selector Editor** or **UI Explorer**.

- 🎯 **Dynamic and Customizable**:  
    You can enhance selectors with:
    - **Variables or expressions** (dynamic selectors)
    - **Wildcards** (`*`, `?`)
    - **Anchor-based targeting**
    - **Fuzzy selectors and descriptors**

- 🚫 **Not Optional**:  
    Selectors are **required** for most UI-based activities to work correctly. Without a valid selector, the robot won't know what to interact with.

### Example of a Selector:

```xml
<wnd app='notepad.exe' title='Document1 - Notepad' />
<ctrl name='Edit' role='editable text' />
```

- This tells the robot to:
	- Look for a Notepad window with a specific title,
	- Then find the text editing area inside that window.

---

## 🧱Structure of the Selectors

| ![[Pasted image 20250504003621.png]] | User Interfaces (UIs) are built using a series of containers nested one inside the other. Let’s take the example of a selector for the First name input field in MyCRM Application, and try to understand the meaning of the structure.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| ------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| ![[Pasted image 20250504141140.png]] | 1. **Root node**<br>	example an application.<br>    `<wnd app='mycrm.exe' ctrlname='Form1' />`<br><br>2. **Node 2**<br>    This identifies the entire area in which data can be edited.<br>    `<wnd ctrlname='tabControl1' />`<br><br>3. **Node 3**<br>    As you can see, the control area has 3 tabs.<br>	This node identifies the People tab.<br>    `<wnd ctrlname='tabPagePeople' />`<br><br>4. **Node 4**<br>    This identifies the Name category of the People tab.<br>	As you can see, there are other categories as well,<br>	and Address is visible.<br>    `<wnd ctrlname='groupBox5' />`<br><br>5. **Node 5**<br>This is in fact the GUI element that interests us. It corresponds to the editable field of the First field.<br>`<wnd ctrlname='textBoxPeopleFirstName' />`<br>`<ctrl name='First:' role='editable text' />` |

---

## 🏷️Tags & Attributes of Selectors

From the image above, we can see that selectors consist of nodes, each of which is composed of tags and attributes.

Let's use an example to illustrate this concept. The following is an illustration of a selector node. 

- **Tags**
	- Nodes in the selector XML fragment.
	- Corresponds to a visual element on the screen.
	- The first node is the app window.
	- The last node is the element itself.
	  
	- For example:
		- **wnd** (window)
		- **html** (web page)
		- **ctrl** (control)
		- **webctrl** (web page control)
		- **java** (Java application control)

- **Attributes**
	Attributes are the characteristics or properties of an element that help identify and interact with it. They provide specific information about the element, such as its name, ID, class, title, or type. These attributes are used to find and perform actions on the desired elements during automation. 
	
	Every attribute has a name and a value. You should use only attributes with constant or known values.
	- For example:
		- parentid=‘slide-list-container’
		- tag=‘A’
		- aaname=‘Details’
		- class=‘btn-dwnl’