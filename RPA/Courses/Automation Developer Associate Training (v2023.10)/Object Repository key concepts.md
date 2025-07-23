## 🗺️Lesson overview

Object Repository provides a structured way for organizing and maintaining the objects, enabling easy reuse and maintenance. By the end of this course, you'll have a comprehensive understanding of these structure and be equipped to apply these concepts to your automation projects.

---

## ⚙️Object Repository structure

Object repository has a tree structure where each node is an object representing screens or elements, all hierarchical under the application. The structure is the following: 

1. **Application -** It can be one of 2 types: mobile or desktop/web, depending on what technology is used for UI Automation. 

2. **Version -** Applications can have multiple versions. 

3. **Screen -** Top-level window of an application version that can only be created under an app version. 

4. **UI Element -** An object on the screen with a descriptor and metadata. It can be of multiple types.

---

## 🗝️Introduction to key concepts

Let's take a moment to focus on the key concepts related to the Object Repository.

- **UI Descriptors**
	A UI Descriptor is a superset of selectors. It holds information for uniquely identifying elements on the screen. UI Descriptors are extracted from activties in the workflow and added to a structured schema that groups them by Applications, Application Versions, Screens, and UI Elements. Out of this taxonomy structure, only Screens and Elements hold descriptor information. The rest are used for grouping and their role is to ensure upgrades between versions of an application. 
	
	- UI Descriptors can be part of:
		- One project for wide reuse.
		- Snippets repositories for testing purposes.
		- UI Libraries for global cross-project sharing.
	
- **UI Applications**
	A UI Application is a targeted application that can have multiple versions and each version can have multiple screens. Applications can be of multiple types: 
	
	- Desktop/ Web Application
	- Mobile Application
	
- **Screens**
	Screens are UI Scopes that are either extracted from activities inside the workflow or are generated at element capture time. A screen groups together multiple elements belonging to the same screen. 
	
- **UI Elements**
	UI Elements contain full or partial element selectors, anchor selectors, screen and element image capture context, and other metadata that describes the element on the screen.
	
- **UI Libraries**
	A UI Library is an encapsulation of elements grouped by applications, application versions, and screens. The elements you define can be extracted as a UI Library, and after publishing, can be installed in other projects as a dependency.
	
	A UI Library may contain several applications but can contain only one version of a certain application. This mechanism ensures that when you upgrade a dependency, you also upgrade the application version you were using inside your projects.
	
- **UI Activities**
	 UI Activities allows you to view a list of all your UI activities inside your process.

>[!NOTE]
>For defining mobile applications, you need to use UiPath.MobileAutomation.Activities package.


---

## ⚙️UI Library structure

The structure of UI libraries created with the Object Browser has the following hierarchy: **Application > Version > Screen > UI Element.** Let's see all the elements depicted below in the process of capturing elements using the Capture Elements recorder in the Object Repository.

| ![[Pasted image 20250505063228.png]] | 1. Application<br><br>This is an example for a versioned Application, used to structure the Screens and UI Elements.<br>--<br><br>2. Screen<br><br>This is an example of a Screen in the DoubleUi App. Screens contain Descriptor information which help identify the app screen and are also used to structure UI Elements.<br>--<br><br>3. UI Element<br><br>This is an example of a UI Element. It contains element identification and Descriptor information. <br><br>You can see the various targeting methods on the right hand side (Target and Anchor).<br>--<br><br>4. Elements Hierarchy<br><br>The elements hierarchy is visible in the left-hand side panel.<br>--<br><br>5. UI Element Properties<br><br>The Properties include the Element Name, Type, Description  and the Descriptor. <br><br>The Element Name, Type and Description help developers identify the object. The Descriptor helps the Robot identify the element on the application screen. <br><br>In this example, the Descriptor includes several targeting methods used  to identify the Not On Us Check field:<br><br>- Strict Selector<br>- Fuzzy Selector<br>- Image<br>- Anchor<br> |
| ------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |

