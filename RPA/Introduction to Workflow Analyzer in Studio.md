## 🗺️Lesson overview

Workflow Analyzer uses a set of rules to check for various inconsistencies unrelated to project execution. The rules are based on automation best practices and take into consideration variable and argument naming, empty sequences or workflows, package restrictions, and so on. The analyzer does not identify errors during execution or compilation.

---

## 🤔What is it?

Workflow Analyzer is a static code analyzer that ensures your project meets high quality and reliability standards. 

When triggered, the Workflow Analyzer uses the configured rule set to check the project or workflow for inconsistencies without executing the project. It logs the errors found in the Error List panel, under the rule action (Error, Warning, Info or Verbose). The rules are based on UiPath Automation Best Practices.

 Using the Workflow Analyzer, you can:

- Edit, disable and enable rules from Studio.
- Run validation or validation and analysis at file or project level.
- Manage errors and warnings in the Error List panel.
- Build custom rules using the UiPath.Activities.Api package.
- Integrate workflow analysis with prebuilt and/or custom rules in CI/CD pipeline configurations.

---

## 🤔Why do you need it?

Workflow analysis plays a central part in project development. Workflow Analyzer is a tool for making sure your project follows best practices, thus ensuring higher quality, reliability and readability.

|                                      |                                                                                                                                                                                                                                                                                                                                                                                                       |
| ------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ![[Pasted image 20250505155409.png]] | **How does it work?**<br><br>You can access the Workflow Analyzer options by clicking the Analyze File drop-down menu from the Design ribbon tab. Running workflow analysis is a two step process. The Analyzer runs workflow validation (checks for compilation errors) first, and only after it passes, it analyzes (checks for breaches against the defined Workflow Analyzer rules) the workflow. |

The workflow analyzer can be enforced using following ways:

| ENFORCE ANALYZER BEFORE RUN                                                                                                                                                                         | ENFORCE ANALYZER BEFORE PUBLISH                                                                                                                                                                                                         | ENFORCE ANALYZER BEFORE PUSH/CHECK-IN                                                                                                                                                                                                                                                   |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| This option runs the Workflow Analyzer before running or debugging a workflow file and checks for all the rules with Error action. It allows execution of the workflow only if no errors are found. | This option runs the Workflow Analyzer before publishing a workflow file or a project. It checks for all the enabled rules regardless of their action and allows publishing only if there are no rule violations with the action Error. |  Whenever sending a project to a remote repository is initiated (Commit and Push for GIT, Check in for SVN and TFS), the Workflow Analyzer checks all enabled rules regardless of their action and the operation is allowed only if there are no rule violations with the action Error. |

**To enable either of these options, access Home > Settings > Design**

When Enforce Analyzer before Publish is enabled, if publishing is successful (there are no rule violations with the action Error) the results of the workflow analysis are included in the published .nupkg package in the file project_analysis_results.json located in \lib\net45\.analysis\.

---

## 💻Workflow Analyzer rules categories

In the analysis stage, your project is checked against a set of predefined rules applicable to Studio. At the moment, there are eight rule categories: 

|                                           |                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| ----------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **NAMING RULES**                          | Rules in this category carry the **NMG** code in their ID. This category checks the file or project for any inconsistencies related to naming. <br><br>Below is the list of rules:<br><br>![](https://academy.uipath.com/content/academy_/scorm/public/learning-plan/0pNfa7zWClLqXTBNwujY1/wjf4Bd8Fxchyx8EUO9wln/VqjDpiQcE0c45IXWUNCCiu5UirIVwgdG_SCORM2004.4_241114_v1/scormcontent/assets/T1.png)                             |
| **DESIGN BEST PRACTICES**                 | Rules in this category contain the **DBP** code in their ID. This category refers to requirements for ensuring your project meets a general set of best practices. <br><br>Below is the list of rules:<br><br>![](https://academy.uipath.com/content/academy_/scorm/public/learning-plan/0pNfa7zWClLqXTBNwujY1/wjf4Bd8Fxchyx8EUO9wln/VqjDpiQcE0c45IXWUNCCiu5UirIVwgdG_SCORM2004.4_241114_v1/scormcontent/assets/T2.png)         |
| **PROJECT ANATOMY RULES**                 | Rules in this category contain **ANA** code in their ID. The rules in this category ensure your project meets general requirements in terms of anatomy. <br><br>Below is the list of rules: <br><br>![](https://academy.uipath.com/content/academy_/scorm/public/learning-plan/0pNfa7zWClLqXTBNwujY1/wjf4Bd8Fxchyx8EUO9wln/VqjDpiQcE0c45IXWUNCCiu5UirIVwgdG_SCORM2004.4_241114_v1/scormcontent/assets/T3.png)                   |
| **MAINTAINABILITY AND READABILITY RULES** | Rules in this category contain **MRD** code in their rule ID. The rules in this category require projects to be easy to understand so that maintainability is ensured. <br><br>Below is the list of rules: <br><br>![](https://academy.uipath.com/content/academy_/scorm/public/learning-plan/0pNfa7zWClLqXTBNwujY1/wjf4Bd8Fxchyx8EUO9wln/VqjDpiQcE0c45IXWUNCCiu5UirIVwgdG_SCORM2004.4_241114_v1/scormcontent/assets/T4.png)    |
| **USAGE RULES**                           | Rules in this category contain **USG** code in their ID. The rules in this category refer to requirements for ensuring elements defined in your project are actually used. <br><br>Below is the list of rules:<br><br>![](https://academy.uipath.com/content/academy_/scorm/public/learning-plan/0pNfa7zWClLqXTBNwujY1/wjf4Bd8Fxchyx8EUO9wln/VqjDpiQcE0c45IXWUNCCiu5UirIVwgdG_SCORM2004.4_241114_v1/scormcontent/assets/T5.png) |
| **PERFORMANCE AND REUSABILITY RULE**      | A rule in this category contains **PRR** code in its ID. The rule in this category checks the file or project for any inconsistencies related to performance and reusability. <br><br>Below is the rule:<br><br>![](https://academy.uipath.com/content/academy_/scorm/public/learning-plan/0pNfa7zWClLqXTBNwujY1/wjf4Bd8Fxchyx8EUO9wln/VqjDpiQcE0c45IXWUNCCiu5UirIVwgdG_SCORM2004.4_241114_v1/scormcontent/assets/T6.png)       |
| **RELIABILITY RULE**                      | A rule in this category contains **REL** code in its ID. The rule is in this category checks the file or project for any inconsistencies related to reliability.<br><br>Below is the rule:<br><br>![](https://academy.uipath.com/content/academy_/scorm/public/learning-plan/0pNfa7zWClLqXTBNwujY1/wjf4Bd8Fxchyx8EUO9wln/VqjDpiQcE0c45IXWUNCCiu5UirIVwgdG_SCORM2004.4_241114_v1/scormcontent/assets/T7.png)                     |
| **SECURITY RULES**                        | The rules in this category contain **SEC** code in their ID. The rules in this category check the file or project for any inconsistencies related to security. <br><br>Below is the list of rules:<br><br>![](https://academy.uipath.com/content/academy_/scorm/public/learning-plan/0pNfa7zWClLqXTBNwujY1/wjf4Bd8Fxchyx8EUO9wln/VqjDpiQcE0c45IXWUNCCiu5UirIVwgdG_SCORM2004.4_241114_v1/scormcontent/assets/T8.png)             |
>[!INFO]
>It is important to keep in mind that various releases may update the categories and rules for each category. Stay up-to-date by reviewing the documentation in the Workflow Analyzer section of the UiPath Studio Guide. 
>
>Also, certain activity packages such as Excel, Mail, Testing, and UI Automation will come with their own workflow analyzer rules. These rules will get added automatically when your workflow uses any of these activity packages.


---

## ⚖️Workflow Analyzer rules components 

Each rule has an ID, name, description, recommendation, scope and default action. Some rules have an editable property.

Note that if you have changed any default parameters and want to revert then right-click the selected rule and select **Reset to Default** option.

Let us have a quick look at each component of the rule.

![[Pasted image 20250505160918.png]]![[Pasted image 20250505160930.png]]
![[Pasted image 20250505160943.png]]
![[Pasted image 20250505160957.png]]
![[Pasted image 20250505161012.png]]![[Pasted image 20250505161029.png]]

---

## 🧭Exporting Workflow Analyzer results

You can configure Studio to export the results of each workflow analysis to the project folder. Go to **Studio Backstage View > Settings > Design** and enable the option **Export Analyzer results**.

When this option is enabled, the results of each workflow analysis are saved in the JSON format in the \.local\.analysis\ subfolder of the project folder. The file will contain the following information about each enabled rule:

- RuleId
- RuleName
- Parameters
- Severity
- ErrorsDescription

>[!INFO]
>The .local folder is hidden. You can enable viewing hidden items from the Windows File Explorer settings.

