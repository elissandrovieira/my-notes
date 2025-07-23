## 🗺️ Overview 

Business processes involve diverse applications and technologies, which can present challenges during UI automation. To ensure a reliable automation process, it's crucial to validate the UI elements and targets during the development phase. 

There are two options available to assess the reliability of your UI automation configuration. 

- Show All Matches
- Target element validation
### Show All Matches

The "Show all matches" feature helps to identify all the possible matches for the selected element within the automated application. This option is useful for debugging UI descriptors or selections, allowing you to ensure the accuracy of your automation setup.

| ![[Pasted image 20250503235750.png]] | The Targeting method show all possible matches to this technique. |
| ------------------------------------ | ----------------------------------------------------------------- |

### Target Element Validation

Target element validation allows you to assess the effectiveness of the current selection in accurately identifying the target. It inspects the generated descriptors for the target using all the selected methods and anchors to provide a validation result, which is displayed at the top of the Selection Options window. If adjustments are required, a message will be shown with guidance on how to improve the selection.

In the Advanced Settings section of the Selection Options window, one of the following icons represents the performance of each method.

**Look at this image:**
![[Pasted image 20250503235952.png]]

1. The method was the first to successfully identify the element, indicated by 🎯.
2. The method successfully identified the element, indicated by ✔️.
3. The method identified duplicates with the equivalent anchor, but at least one other anchor has worked. It is indicated by 📑.
4. The method failed to identify the element, indicated by 🚫.