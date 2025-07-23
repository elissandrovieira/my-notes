## Overview

From the **[[User Interface (UI) Automation with Modern Design in Studio]]** course, we briefly covered the targeting methods used in UI automation. Now, let's reinforce our understanding by answering a few questions and reviewing the key concepts. 

Now, let's answer a couple of questions related to this topic and take a quick glance at the recap to reinforce these basic concepts.

- **What's targeting methods in UI automation?**
	Techniques used to identify and interact with a specific target user interface element to perform the required action on it.

- **Which are the key targeting methods used in UI automation to identify UI elements?**
	- ***Strict Selectors***
		Is a **fully defined XML path** to an element in the UI. It uses **fixed attributes** like `aaname`, `idx`, `title`, `id`, etc.
		-  **Best for:**
			- **Stable UIs** with consistent structure
		    - Apps where elements don't change their attributes often
		- Drawback:
			- **Breaks easily** if any attribute or window title changes	    
		-  Example:
			```xml
			<wnd app='chrome.exe' title='Inbox - Gmail'/>
			<ctrl name='Compose' role='push button'/>
			```

	- ***Fuzzy Selectors***
		Use **fuzzy logic** (similarity scoring) to **match elements that are close** to what you defined — even if the selector is not exact.
		- **Best for:**
			- **Slightly dynamic UIs**
		    - When attributes may change slightly (e.g., different languages or labels)
		- **How it works:**
			- UiPath analyzes and scores nearby elements based on **partial match**
			- Combines multiple indicators like element structure, position, and text
		- **Drawback:**
			- **Less precise**, so may match the wrong element if the UI is crowded
		- Looks like:
			It’s not shown in XML like strict selectors — it’s managed by UiPath internally when you enable “Fuzzy” in the UI Explorer.
	
	- ***Computer Vision***
		Uses AI to "see" UI elements visually — like a human would — by analyzing screenshots and detecting elements **based on their layout, labels, and screen appearance**, even when the traditional UI selectors fail.
		- **Best for:**
			- **Remote environments** (Citrix, RDP)
			- **Web pages or apps** where selectors are hidden, dynamic, or inaccessible
			- Cases where **strict or fuzzy selectors don’t work**
	    - **Strengths:**
			- Recognizes **text and visual layout**, not code
			- Works even when **UI framework changes**
			- Adds **resilience** to automation
	    - **Drawbacks:**
			- Requires **internet connection** (since CV runs in the cloud)
			- Slightly **slower** than native selectors
		- **Tools used:**
			- `CV Screen Scope`
			- `CV Click`, `CV Type Into`, etc.
	
	- Image
		Uses **pixel-by-pixel comparison** to find an image **snapshot** (like a button or icon) on the screen.
		- ***Best for:***
			- **Virtual environments** (Citrix, RDP)
		    - When no selectors are available (like in games or legacy systems)
		- ***Drawbacks:**
			- Sensitive to:
			    - Resolution
			    - Theme/contrast changes
			    - UI updates
			- Slower and less reliable than selectors
		- ***Tools used:***
			- `Click Image`
			- `Find Image`
		    - `Image Exists`
	
	- ***Window Selector***
		Targets the **entire application window** rather than a specific UI element within it. It defines the **application scope** for activities inside the workflow.
		- **Best for:**
			- Automating interactions at the **app or window level**
		    - Scenarios with **multiple windows or popups**
		    - Controlling **when to attach to or detach from a window**
	    - **How to use:**
			- Use inside the `Use Application/Browser` activity
		    - Set **"Window Attach Mode"** properly:
		    - `Single window`: attaches to a specific window
            - Other modes: allows flexibility across multiple windows
		- **Strengths:**
			- Useful for defining **UI scope**
		    - Helps manage **window focus** and isolation of activities
		- **Considerations:**
			- Doesn’t target individual controls — used for **scoping**

---
## Summary Targeting Methods Table

| Targeting Method     | Strengths                                                              | Weaknesses                                                          | Ideal Use Case                                          |
| -------------------- | ---------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------- |
| **Strict Selectors** | Precise, fast, easy to inspect and edit                                | Breaks with small UI changes (title, idx, etc.)                     | Stable web/desktop UIs                                  |
| **Fuzzy Selectors**  | Flexible with attribute variations, resilient to small UI changes      | Risk of false positives; less deterministic                         | Semi-dynamic UIs with changing labels or structures     |
| **Image Selection**  | Works where selectors fail; easy to implement                          | Fragile to resolution/theme changes; slower                         | Citrix, remote desktops, legacy apps                    |
| **Computer Vision**  | AI-driven, identifies UI by visual layout and labels; highly resilient | Requires internet connection; slightly slower than native selectors | Dynamic UIs, virtual environments, selector-less UIs    |
| **Window Selector**  | Defines app scope; handles multiple windows; manages window focus      | Doesn’t target individual UI elements directly                      | Application-level automation, managing multiple windows |

---

## Targets and Anchor concepts

### What's Target?

A target refers to a specific UI element that we want to interact with. It could be any component on the user interface, like a button, textbox, or dropdown list. 

For example, if we have a login form, the "Submit" button and the "Username" and "Password" textboxes would be considered targets. 

  
### To ensure accurate identification of targets, we can use an anchor.

An anchor is an additional UI element that helps in identifying the target. Anchors are particularly useful when potential conflicts are detected in the selection window. By incorporating multiple anchors, we enhance the reliability and accuracy of our automation.

When working with modern UI automation activities, an anchor is automatically selected for you. However, you can also manually configure the anchor selection if needed. It's important to note that you can add up to three anchors to a single target, maximizing the reliability of your automation.