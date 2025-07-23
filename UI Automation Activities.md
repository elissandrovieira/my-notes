## 🗺️Overview

From the [[User Interface (UI) Automation with Modern Design in Studio]] course, we learned about the essential components of UI automation. These include UI Automation activities, Activity properties, Targeting methods, and Input and Output methods. Together, these components enable developers to effectively interact with the interfaces of various applications.

---
## Key UI Automation concepts

- **Activities**
	Tell the Robot what actions to take.
- **Properties**
	Determine how Activities behave.
- **Targeting methods**
	Identify the UI Element to take an action on.
- **Input and output methods**
	Define how what technology is used when sending input or getting output from an UI.

---

## Categories of UI Automation Activities in UiPath

-  **Containers**
	- Define the scope for UI interactions
	- Used to group related activities
    
	- Examples:
	    - _Use Application/Browser_
	    - _Attach Window_
	    - _Open Browser_

- **Input Activities**
	- Simulate user interactions
	- Send data to UI elements
    
	- Examples:
	    - _Click_    
	    - _Type Into_    
	    - _Select Item_

- **Output Activities**
	- Extract information from the UI
	- Useful for reading data from screens
	- 
	- Examples:
        - _Get Text_
        - _Get Attribute_
        - _Screen Scraping_

-  **Synchronization Activities**
	- Handle timing and UI state
	- Wait for elements to be ready
	- 
	- Examples:
	    - _Element Exists_
        - _Wait Element Vanish_
        - _On Element Appear_