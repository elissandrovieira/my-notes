## 🗺️Overview

As previously explained, selectors are automatically generated when UI elements are identified within activities or when using the recorder. Understanding the difference between full and partial selectors becomes essential when activities are generated using different design experiences in UiPath Studio.

---
## 🔧Full Selector

| ![[Pasted image 20250504144142.png]] | - Full selectors contain all necessary information to identify a specific UI element, including the top-level window.<br><br>- Full selectors are commonly used in the Classic Design Experience, while modern design uses partial selectors for child activities within containers. |
| ------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
|                                      |                                                                                                                                                                                                                                                                                      |
## 🔧Partial Selector

| ![[Pasted image 20250504144503.png]] | - Partial selectors are specific to container activities and store information related to the top-level window.<br><br>- In modern design, the selector combines information from the container activity and the child activity(partial selector) to accurately identify the UI element. So, in the end, this combination build a full selector. |
| ------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
|                                      |                                                                                                                                                                                                                                                                                                                                                  |