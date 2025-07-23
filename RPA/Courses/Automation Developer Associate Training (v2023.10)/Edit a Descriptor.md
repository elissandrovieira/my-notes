## 🗺️Lesson overview

In this lesson you will understand how descriptor can be edited in different scenarios.
Let's take a closer look at each of them!

---

## ✏️Editing Descriptors in Object Repository 

Descriptors can be edited from the Object Repository in two scenarios:

| ONLINE EDITING                                                                                                                                                                  | OFFLINE EDITING                                                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| In the Descriptors tab, right-click an element and select Edit Descriptor. The selection screen opens allowing you to capture a different element, edit selectors, and anchors. | The application or browser can not be accessed on the current machine; either due to the app not being installed, or the machine is offline. The element's selectors are made visible allowing changes to be made. |
| ![[Pasted image 20250505071710.png]]                                                                                                                                            | ![[Pasted image 20250505071719.png]]                                                                                                                                                                               |

---

## 🧭Exploring Screen Descriptors 

You can also edit a screen descriptor, in the descriptor tab.

You can edit the application path or browser URL, application arguments, window selector, and select whether only applications with a title that is an exact match can be used in the automation. 

These fields support expressions, variables, and arguments. To do this, right-click the screen and select Edit Descriptor. The Edit Screen window is displayed.

![](https://academy.uipath.com/content/academy_/scorm/public/learning-plan/VHstOacrJGuXlPemuyXmw/1gImSvmbVeA7fDGGkrDHxh/6wSw-t3NbEJthbq6_TTAMTXiuVDUAARg_SCORM2004.4_240918_v2/scormcontent/assets/screen%20descriptor_NOPROCESS_.png)

---

## 🪛Resolving UI Descriptors  

Whenever you indicate a screen or UI Element which is already referenced in the Object Repository either under Project UI Descriptors or UI Libraries, the match is automatically detected and the following window is prompted: 

![](https://academy.uipath.com/content/academy_/scorm/public/learning-plan/VHstOacrJGuXlPemuyXmw/1gImSvmbVeA7fDGGkrDHxh/6wSw-t3NbEJthbq6_TTAMTXiuVDUAARg_SCORM2004.4_240918_v2/scormcontent/assets/Screen_NOPROCESS_.png)


**The following options are available:**

| REUSE                                                                               | CREATE NEW                                                                                                          | CANCEL                                                                                                                  |
| ----------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------- |
| It adds the matching descriptor from the Object Repository to the current activity. | It opens the options window for creating a new screen/element or updating an existing one in the Object Repository. | It keeps the currently indicated selector inside the activity, without making any changes to objects in the repository. |

Indicating a screen searches for a corresponding UI descriptor, while indicating a target element searches for a matching UI descriptor. When using the Recorder, corresponding matches for screen and elements are searched within the local UI library from Project UI Descriptors or the imported dependencies from UI Libraries.

>[!NOTE]
>At runtime, the UI Descriptors are resolved from the Objects Browser panel, if the activities reference such UI Descriptors.

---

## 📥Incorporating Variables in Descriptors 

Descriptors use variables to increase the degree of reusability. You can edit a target, add variables to it, and then add it to the Object Repository, or you can add variables to selectors in existing screens or elements from the Object Repository. Whenever you add a descriptor that contains a variable to a process, make sure to create the variable in the process, otherwise the expression cannot be read.

|                                      |                                                                                                          |
| ------------------------------------ | -------------------------------------------------------------------------------------------------------- |
| ![[Pasted image 20250505072323.png]] | **For example:**<br><br>Create a new variable 'EmployeeName', and assign it to the 'InnerText is’ field. |

Variables can also be used inside the Browser URL field of the Use Application/Browser activity and then added the target as screen objects to the Object Repository. As a result, you will ensure that the descriptor accounts for changing URLs.

![[Pasted image 20250505072459.png]]