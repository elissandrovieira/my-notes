## 🗺️Overview

Fine-tuning descriptors in automation workflows is crucial for enhancing the reliability and adaptability of the automation process. This involves refining and adjusting descriptor configurations to improve accuracy and overcome challenges like unreliable selectors or dynamic UI elements. While manual editing of descriptors is generally not recommended, there may be rare cases where fine-tuning the Unified targeting method becomes necessary due to unreliable descriptors. Fortunately, there are various techniques available to effectively fine-tune descriptors in such cases.

In this lesson, we'll focus on scenarios where a required UI element lacks a unique name, reliable anchor, or undergoes dynamic changes upon webpage refresh. We'll explore techniques such as the **dynamic text target option**, **using wildcards**, the **repair function**, **variables**, and **adjusting image accuracy** to address these challenges.

---

## 🗝️Key Actions for Fine-Tuning Descriptors

Here are the key actions to fine-tune targeting methods and achieve optimal results:
### Evaluate Targeting Method Reliability

- Use the Validation option to assess the reliability of each targeting method.
- Evaluate the accuracy and consistency of the Selector, Fuzzy Selector, and Image methods.
- Fine-tune a targeting method using the best suitable technique if it consistently fails or produces unreliable results.
- 
### Adjust Fuzzy Selector Settings

- Fine-tune the Fuzzy Selector to handle attribute variations and dynamic elements.
- Increase the accuracy in matching the target element.

### Optimize Image Targeting

- Fine-tune image settings, such as accuracy, to improve matching for dynamic UI elements. 

### Prioritize Targeting Methods

- Choose the appropriate targeting method based on reliability and effectiveness.
- Adjust the order in which the targeting methods are executed to prioritize the most reliable method.

### Test and Iterate

- Thoroughly test the automation workflow under different scenarios.
- Iterate and fine-tune further as necessary to achieve optimal results.

---

## 🃏Fine-tuning Descriptors using Wildcards

When selectors contain **static values**, such as exact file names or timestamps, automations can fail if the UI element changes slightly—like when a different document is opened or the window title varies.

This is common in real-world automation: the robot might work for one file or session but fail on another due to a small difference in the selector string.

**Wildcards** offer a flexible way to handle these variations by allowing **partial matching**. Instead of matching an exact value, the selector can match a **pattern**.

Using wildcards makes selectors more **dynamic**, **resilient**, and **reusable**, especially when automating repetitive tasks across multiple files or variable interface elements.

- ***Wildcard Types in UiPath Selectors***
	- **Asterisk (`*`)**
	    
	    - Replaces **zero or more characters**.
	    - Use it when an attribute value can change completely or vary in length.
	    - Example use: file names, timestamps, session IDs.
	    
	- **Question Mark (`?`)**
	    
	    - Replaces **exactly one character**.
	    - Use it when only a single character may change and the length stays fixed.
	    
	
	These wildcards can be manually inserted into the selector (through the **Selector Editor**) or generated using the **Repair** function when a selector breaks.

- ***Example Scenario***
	- **Task:**
		Create a workflow to **remove double spaces** from any Notepad file using the Replace (Ctrl+H) command.
	
	- **Initial Problem:**
		The robot works on a specific file (e.g., `"Text1.txt"`) but fails when the file name changes to `"Text2.txt"` because the selector for the window title doesn’t match.
	
	- **Solution:**
		1. Identify the title attribute in the selector.
		2. Replace the specific file name portion with:
		    - `?` if only a character or digit changes (e.g., `"Text?.txt"`),
		    - `*` if the name changes entirely or has variable length (e.g., `"*.txt"`).
	
	- **Result:**
		The automation successfully runs across multiple Notepad files, regardless of name, making it flexible and reusable.

---

## 📤 Fine-tuning Descriptors using Variables

- Variables and arguments can be used in the Strict Selector or Fuzzy Selector to identify the desired target, either by creating new variables/arguments or selecting from existing ones in the context menu.
- The matching accuracy of the Fuzzy Selector can be adjusted using the Accuracy slider to optimize its performance in selecting targets.
- The Image targeting method can be fine-tuned by adjusting the Image Accuracy using its corresponding slider. This allows for precise control over the accuracy of image-based targeting, ensuring reliable identification of target elements based on visual cues.

![[Pasted image 20250504003102.png]]