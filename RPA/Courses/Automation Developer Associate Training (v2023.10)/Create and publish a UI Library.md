## 🗺️Lesson overview

The objective of this lesson is to familiarize you with the various options available for creating an Object Repository in Studio to build and automate applications. You will gain a comprehensive understanding of different approaches for managing object repositories effectively.

---

## ⚙️Object Repository creation options

An object repository is a collection of elements grouped by applications, versions, and screens. It can come from a local project, i.e. the local repository, or from a library, i.e. UI Library dependencies.

- Creating a Local Repository
	- You can create Local Repository by Capture Elements recorder to capture UI descriptors.
	- Also , you can manually create applications, screens, and elements directly in the Object Repository panel.
	
- Creating a UI Library
	- You can extract the local repository from any project into a library project and publishing it as a NuGet package.
	- You can start from a new library, build the repository there, and publish it as a NuGet package. 

You can then use the UI Library NuGet packages and add them as dependencies to your processes.

>[!NOTE]
>The Capture Elements recorder only records objects for reuse in projects, the recorder does not generate a workflow in the Designer panel.


---

## 💻Object Repository Panel 

Object Repository panel provides several features and functionalities that can be leveraged to create and reuse UI taxonomies inside and across projects. 

- You can create a repository using Capture Elements button in the Object Repository. With the Capture All Elements feature, you can capture all the elements of an application using Computer Vision and add them to your Object Repository.

- You can create a  new library that can be installed in other projects as a dependency. Also, you can update an existing library if you exit the recorder before capturing all the desired.

- You can add descriptors to the Snippets panel to reuse them, or extract them as UI libraries.

- You can access objects from UI libraries installed as dependencies to the current project.

Let's take a look of all the options available in Object Repository panel.

| Expand All                                           | Collapse All                                           | Refresh                                     | Add a new Element under this screen         | Capture Elements        |
| ---------------------------------------------------- | ------------------------------------------------------ | ------------------------------------------- | ------------------------------------------- | ----------------------- |
| Expands all of the categories in the Descriptor tab. | Collapses all of the categories in the Descriptor tab. | Refreshes the content of Object Repository. | Add a new Element under the selected screen | Use to capture elements |

---

## 🤚Manual Creation of a Repository

You can create your own repo from within the Object Repository panel by defining the application, each screen, and element manually.

| CREATE A           | EXPLANATION                                                                                                                                                                                                                                                                                                                                                                                                                                                                    | IMAGE                                |
| ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------ |
| **UI Application** | You can create a UI application by clicking on the plus sign in the Descriptors tab or right-click Project Descriptors in the same tab and select Create Application. Add a unique application name, version, and description. Click Create application. Your application is visible in the Descriptors tab, under Project UI Descriptors.                                                                                                                                     | ![[Pasted image 20250505064519.png]] |
| **Screen**         | You can create a screen by selecting an app for example here Calculator app, click the plus sign or right-click your application and select Create Screen. The Add Screen window opens, add a unique name for the screen, and a description. Indicate the screen that you would like to automate, and edit the captured element with Unified Target:<br><br>- change the application path if needed.<br>- add application arguments.<br>- When completed, click Create screen. | ![[Pasted image 20250505064549.png]] |
| **UI Element**     | You can create a UI Element by selecting the app screen, click the plus sign or right-click the screen and select Create Element. The Add Element window opens: <br><br>From the Descriptor Type section click Indicate element to use Unified Target to indicate and capture the element from the screen.<br><br>Add an intuitive name in the Element Name field, and select the type of the element from the drop-down list under Type. Click Save when done.                | ![[Pasted image 20250505064606.png]] |

> [!NOTE]
> - To edit an element from the Object Repository, right-click it, and then select Edit Element, or double-click the element in the tree.
> - To edit the descriptor of an element, use the Edit Descriptor option from the Edit Element window, or right-click the element in the tree, and then select Edit Descriptor.

