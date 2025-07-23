## 🗺️Overview

Asynchronous activities in UiPath Studio enable parallel execution and non-blocking operations, enhancing the performance and flexibility of automation workflows. These activities allow tasks to run independently, reducing waiting times and increasing efficiency.

---

## 🌊Let's delve into the Parallel activity and explore its capabilities

-  **What is it?**
	The Parallel Activity in workflow design allows for the simultaneous execution of multiple independent tasks within a workflow. It acts as a container for activities, facilitating coordinated and concurrent execution. 
    
    In UiPath Studio, the Parallel activity can be found in the **Activities** panel, under **Workflow** > **Control** > **Parallel.**
    
    The Parallel activity finishes only after all child activities are complete or when its `CompletionCondition` property evaluates to true. 
    
- **Why is it important?**
	The parallel allows these tasks to be done at the same time, without waiting for each other.
    
- **Where do I use it?**
	It's ideal for scenarios involving parallel processing, multitasking, or handling multiple events or conditions simultaneously.  
      
    **For example:**  
	    You have a requirement to monitor multiple folders in a system, and you want to implement a solution that can handle the monitoring of these folders concurrently. By using Parallel Activity, you can streamline the process and achieve efficient monitoring.

---

## 🔍Here are some use cases where asynchronous activities can be beneficial in automation workflows 

- **Data retrieval and processing**
	When fetching data from multiple sources or APIs, asynchronous activities can be used to make concurrent requests, speeding up the data retrieval and processing tasks. 

- **File operations**
	When performing operations like copying, moving, or deleting files in bulk, using asynchronous activities can help improve the overall speed and efficiency of the file handling process. 

- **Web scraping**
	Asynchronous activities can be employed for scraping data from multiple web pages simultaneously, reducing the overall execution time of the scraping task. 

- **Database operations**
	When executing database operations such as querying, updating, or inserting data into multiple tables or databases, asynchronous activities can be used to parallelize the tasks and improve overall database performance. 

- **API integrations**
	Asynchronous activities are valuable in scenarios where multiple API calls need to be made concurrently, enabling efficient integration with external systems and reducing response time.

- **Long-Running tasks**
	For tasks that require substantial processing time, such as large-scale data transformations or complex calculations, asynchronous activities can be utilized to perform the operations in the background while allowing the workflow to continue with other tasks. 

- **Distributed processing**
	In scenarios where automation processes need to be executed across multiple machines or robots, asynchronous activities enable parallel execution, maximizing resource utilization and reducing the overall execution time.

---
![[Pasted image 20250503152045.png]]
---
## It is like a [[Threads, mutexes and concurrent programming in C]]?

No, the sequences run in the same process. So, why I would use the parallel activity?
If you want continue running your automation even if one of the sequences inside parallel activity is waiting something.

The **Robot (execution process)** goes through the **branches one at a time**, **in order**, like this:

### ✅ How the UiPath `Parallel` activity works

1. **Starts with Branch A**:
    - Executes activities **until**:
        - The branch finishes, or
        - It reaches a **blocking activity** (e.g. `Delay`, `Element Exists`, etc.)
        
2. Then it **moves to Branch B**, and does the same.
3. Then **Branch C**, and so on...

### 🔁 Then it loops again

Once it’s gone through all branches once, it starts again:
- Resumes any **waiting branches** that are now unblocked.
- Keeps going **until all branches are done**.