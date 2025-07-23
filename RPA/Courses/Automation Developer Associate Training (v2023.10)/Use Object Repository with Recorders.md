## 🤔What is a recorder?

Recorder allows you to identify and record UI elements' properties and attributes that need to be included in your repository.

---
## ✏️Creating a Repository by Capturing Elements

You can click on the Capture Elements button in the Object Repository to open the Capture Elements recorder. For capturing elements, click Start recording. With the Capture Elements recorder, you can capture targets, anchors, and images with a degree of accuracy using the Unified Target technology found in the UIAutomation.Activities pack version 20.10 or higher.

### 1. How to use Object Repository with Recorders

![](https://academy.uipath.com/content/academy_/scorm/public/learning-plan/VHstOacrJGuXlPemuyXmw/1gImSvmbVeA7fDGGkrDHxh/6wSw-t3NbEJthbq6_TTAMTXiuVDUAARg_SCORM2004.4_240918_v2/scormcontent/assets/Recorder_NOPROCESS_.PNG)

An informative tooltip informs you to add descriptors to the Object Repository or use existing ones.

You can add or reuse descriptors by clicking on the icon inside the activity, or you can select **Options > Add to Object Repository** to add the element.

### 2. How to add elements from Activities to a Repository

![](https://academy.uipath.com/content/academy_/scorm/public/learning-plan/VHstOacrJGuXlPemuyXmw/1gImSvmbVeA7fDGGkrDHxh/6wSw-t3NbEJthbq6_TTAMTXiuVDUAARg_SCORM2004.4_240918_v2/scormcontent/assets/adding%20activity_NOPROCESS_.png)

You can add more UI elements directly from the Designer panel that supports selectors, like Click or Type Into. 

Click the Object Repository icon within the activity body to open the Selection Options window. Capture the element and select Confirm. Once the Add Element to Object Repository window opens, give the element a name and click Finish.

### 3. Use Objects in a current project

![](https://academy.uipath.com/content/academy_/scorm/public/learning-plan/VHstOacrJGuXlPemuyXmw/1gImSvmbVeA7fDGGkrDHxh/6wSw-t3NbEJthbq6_TTAMTXiuVDUAARg_SCORM2004.4_240918_v2/scormcontent/assets/dragobject_NOPROCESS_.png)

You can drag and drop a screen or element on top of an activity in your workflow using Object Repository. The object's image, arguments, and other details are automatically added to the activity. When an activity uses a screen or element from the Object Repository, clicking the Object Repository icon in the activity highlights the descriptor it uses in the Object Repository tree. 

In the below example, UIDemo screen is dragged on top of the Use Application/Browser activity. The application path is automatically added to the activity.