There are two easy ways to start a project with the Spring Framework:
 - Using **IntelliJ IDEA Ultimate**;
 - Using **Spring Initializer** web page.

## Spring Initializer

In the Spring Initializer, there are some options:
- Project - To choose the **Build Automation tool**.
	- **Build automation tools** are widely used in Java projects (such as those with Spring). They help to:
		- Manage dependencies (libraries your project needs)
	    - Compile code
	    - Run tests
	    - Package the project (into .jar, .war, etc.)
	    - Run the app or deploy it
	- The most used in nowadays is **Maven**
- **Dependencies**
	- Dependencies are like `npm packages`.
	- For the most part of the projects, you will use the **[[Spring Web(Tomcat)]]** dependency.
- **Project Metadata**
	- Group
		- Is the controller group domain, but the `.com` or another option is in the begin.
		- Ex: google.com -> com.google
	- Artifact
		- Is the directory project name
	- Name
		- Is the project name
		- For convention, is a good pratice Artifact and Name have the same name.
	- Description
		- Is the project description
	- Package name
		- Is the Java package name
		- Usually is the Group+Artifact join
		- Ex: com.google.Gemini
	- Packaging
		- Is common use `Jar`
	- Java
		- Java version to the project

After, you can download this project and open it at your favorite IDE.