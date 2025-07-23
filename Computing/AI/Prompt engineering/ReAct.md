## Overview

Is a few-shot prompting technique, but is different than the chain of thoughts([[COT]]).

While COT reasoning step by step until to arrive in the response, the ReAct goes one step further. It's not only the reasoning with the input, but acting based on what else is necessary to arrive at the response.

- Combines **reasoning (like CoT)** _and_ **taking actions in the environment** (like querying APIs, searching docs, or using tools) within the same interaction loop.
    
- The model **reasons about what to do next**, **acts** (e.g., makes a search query), **observes the result**, then reasons again — iterating until it finds an answer.

## Flowchart


![[ReAct.jpg]]