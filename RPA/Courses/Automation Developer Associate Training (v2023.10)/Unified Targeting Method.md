## 🗺️Overview

The Unified Target method, a modern solution for UI automation, simplifies the interaction with user interfaces by incorporating various technologies and methods like Selectors, Fuzzy Selectors, and Images to identify UI elements. 

By using a unified targeting method, the different methods within it complement and support each other, enhancing the reliability of UI automation. This means that even if one method encounters difficulties in selecting a UI element, other methods can step in to overcome the obstacle.

## Key advantages of using the Unified Target method

One of the key advantages of using the Unified Targeting method is its versatility and ease of use. It provides a ready-to-use solution that seamlessly integrates into workflows without the need for complex configuration or considering individual method-specific details. This makes it highly convenient and efficient for developers and automation engineers.  

To identify UI elements, the Unified Targeting method uses a combination of UI frameworks.

| ![[Pasted image 20250503234718.png]] | By default, a proprietary framework is used, but alternative options like AA (Active Accessibility) and UIA (Microsoft UI Automation) are available based on the target application's type. |
| ------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |

- A Unified Target consists of at least one target, along with optional anchors. 
	
- Each UI element is located using a stack of targeting methods, including **Strict Selectors, Fuzzy Selectors, and Images**. 
	
- These targeting methods work redundantly, simultaneously attempting to identify the target element. The first method that successfully finds the target is considered.


| ![[Pasted image 20250503234924.png]] | Different sections within the project settings cater to specific types of target applications, allowing for easy configuration. |
| ------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------- |

---

## Descriptor

To understand Descriptors, let's consider a practical example of a **Type Into** activity for the "Cash In" input field. In this case, we want to enter data into the "Cash In" field, which has a corresponding label.


| ![[Pasted image 20250503235055.png]] | In this scenario, we have an input field labeled "**Cash In**" where we want to enter data. Additionally, we have an anchor associated with the **corresponding label**. <br><br>The **Target** here's the **input field**, and the **Anchor** is the **label**. |
| ------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
During runtime, the robot uses three targeting methods, namely **Strict Selector**, **Fuzzy Selector**, and **Image**, to identify the **Target (Cash In input field)** and the **Anchor (Cash In label)**.

This means there are three targeting methods available to identify the Target and Anchor, resulting in a total of nine possible combinations (3 x 3) of 'Target - Anchor' pairs.

### The Target and Anchor pair is known as Descriptor


| ![[Pasted image 20250503235242.png]] | Under the hood, the robot generates these nine unique combinations, which are known as Descriptors. Each Descriptor represents a unique combination of the identified Target and Anchor elements using their respective targeting methods.<br><br> |
| ------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
By generating these Descriptors, the robot establishes a connection between the input field and its associated label.

The robot runs all nine combinations simultaneously, searching for a successful pair without being limited to any specific targeting method. When a matching pair is found, the robot executes the Type Into activity, allowing us to enter the desired input to the "Cash In" field.

>[!WARNING]
>**Keep in mind that the number of combinations depends on the number of anchors. A target can have up to three anchors associated with it.**

