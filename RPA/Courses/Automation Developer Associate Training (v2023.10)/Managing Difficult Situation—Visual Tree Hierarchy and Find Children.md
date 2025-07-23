## 🗺️Overview 

In some cases, the automatically generated selectors may not be reliable enough and may need adjustment to resolve the issue. However, there are situations known as "difficult" where dealing with UI elements that change their state, position, or ID with each workflow run poses a challenge.

## 🌿Other approaches to use

- **Visual tree hierarchy**
	The hierarchy in the Visual Tree can enhance the reliability of a selector by incorporating the tags and attributes of the element above it in the hierarchy.
	
	This becomes particularly valuable when the selector for the target UI element is unreliable, but the selector for the UI element immediately above it in the hierarchy is reliable. However, it is important to note that the selector still requires additional editing and validation. The dynamic component needs to be removed while ensuring that the target element can still be identified with a unique attribute.
	
- **Find children**
	This activity can identify all the children of an element that's more stable. Since its output is the collection of children, you'll need to come up with a mechanism to identify only the target using one of its attributes, that makes is unique between the children, but wouldn't be enough to identify it universally (UI).