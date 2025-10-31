Big O notation is a mathematical way to describe how the execution time (or space usage) of an algorithm grows as the size of the input increases. It focuses on the _worst-case scenario_ rather than the average or best case.

It is not about raw performance, but about **scalability**—how well an algorithm handles larger and larger inputs.

When analyzing an algorithm, we usually measure two kinds of complexity:

- **Time complexity** → how the runtime increases with input size.
	- Example: 
		- Linear search in an array → **O(n)**
		- Binary search in a sorted array → **O(log n)**
- **Space complexity** → how the memory usage increases with input size.
	- Example: 
		- Storing a copy of an array while reversing → **O(n)**
	    - Reversing an array in place (swapping elements) → **O(1)**

There are many common notations to represent time complexity, including:

- **O(1)** – _constant time_: the runtime does not grow with the input size.
- **O(n)** – _linear time_: the runtime grows proportionally with the input size (the algorithm must process all elements).
- **O(log n)** – _logarithmic time_: the runtime grows much slower than the input size, usually because the problem size is reduced at each step (e.g., binary search).
- **O(n²)** – _quadratic time_: the runtime grows proportionally to the square of the input size, often seen with nested loops.

## Pronounciation

- **O(1)** → _“big O of one”_ → constant time
- **O(log n)** → _“big O of log n”_ → logarithmic time
- **O(n)** → _“big O of n”_ → linear time
- **O(n log n)** → _“big O of n log n”_ → linearithmic time
- **O(n²)** → _“big O of n squared”_ → quadratic time
- **O(n³)** → _“big O of n cubed”_ → cubic time
- **O(2ⁿ)** → _“big O of two to the n”_ → exponential time
- **O(n!)** → _“big O of n factorial”_ → factorial time

## Example in phrases

- _“This algorithm runs in **big O of n** time, which means it scales linearly with the input size.”_
- _“Binary search has a **time complexity of big O of log n**, which is very efficient.”_
- _“Quicksort has an **average time complexity of big O of n log n**.”_

---

Big O is a powerful tool to compare algorithms and understand their scalability, but it does not tell you the exact runtime—it only describes the growth trend.