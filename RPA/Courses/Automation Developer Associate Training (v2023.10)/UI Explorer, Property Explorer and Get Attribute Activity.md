## 🗺️Overview

The UI Explorer is a versatile tool that's available for use with the **UiPath UIAutomation activities** package. It comes to the rescue for selector analysis, modification, and optimization. Its capabilities prove particularly beneficial in troubleshooting selector issues, handling dynamic user interfaces, comprehending complex UI structures, adapting to UI updates, and promoting the reuse of selectors across various automation scenarios. 

The Property Explorer is a component in the UI Explorer that is helpful for analyzing the different attributes of a UI element.

---

## 💻The UI Explorer Interface

| 1   | ![[Pasted image 20250504145040.png]] |     |
| --- | ------------------------------------ | --- |
| 2   | ![[Pasted image 20250504145132.png]] |     |
| 3   | ![[Pasted image 20250504145151.png]] |     |
| 4   | ![[Pasted image 20250504145223.png]] |     |
| 5   | ![[Pasted image 20250504145250.png]] |     |
| 6   | ![[Pasted image 20250504145307.png]] |     |
| 7   | ![[Pasted image 20250504145332.png]] |     |
| 8   | ![[Pasted image 20250504145349.png]] |     |
| 9   | ![[Pasted image 20250504145411.png]] |     |

---

## 🗝️The key functionalities of UI Explorer

- **Validate button**
	
	The UI Explorer includes a validate option, which indicates the state of the selector. It helps users quickly identify any issues or errors within the selector and troubleshoot them effectively. By monitoring the selector's status, users can ensure its accuracy and reliability. 
	
- **Visual tree panel**
	
	The UI Explorer features a visual tree panel that displays a hierarchical representation of the user interface elements in a opened application. This panel allows users to navigate through the UI structure and select the desired element for analysis and editing. The visual tree panel provides a visual overview of the application's UI, making it easier to identify and choose specific elements. 
	
- **Tags and Attribute Display and Inclusion/Exclusion of Tags and Attributes**
	
	The UI Explorer in modern design provides a comprehensive view of the selected UI element's associated tags and attributes, enabling users to understand the element's characteristics and make informed decisions when modifying selectors. Users can review, adjust, and customize the tags and attributes to create more accurate and reliable selectors for automation. 
	
	Furthermore, the UI Explorer allows users to check tags and attributes in or out, granting them greater control over the selector's composition by including or excluding specific properties.

___

## 🔍Property Explorer

| ![[Pasted image 20250504145717.png]] | The Property Explorer allows users to explore a wide range of attributes that define the characteristics and behavior of the UI element. These attributes may include properties like text, position, visibility, and many others. By delving into the details provided by the Property Explorer, users can gain insights into how the UI element behaves and functions within the user interface. <br><br>Analyzing the attributes through the Property Explorer helps users make informed decisions when modifying selectors. By understanding the behavior and properties of the UI element, users can optimize the selectors to accurately interact with the desired element during automation. |
| ------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |

---

## 🔦Event Inspection Tool
#lookat

The Event Inspection Tool can be opened from the UI Explorer, once a valid UI element is selected, by clicking the Inspect Events toolbar button.

| ![[Pasted image 20250504145939.png]] | In the context of trigger-based attended automation, the Event Inspection Tool can be used to identify the type of native events triggered when you interact with certain UI elements in an application, and then it can be used for configuring the Application Event Trigger activity. The tool captures and monitors all the selected event types, such as Click, Key pressed, Focus gained, Focus lost, and other relevant interactions, enabling you to analyze the actions performed and, if applicable, diagnose issues. |
| ------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
