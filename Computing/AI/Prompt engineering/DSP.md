## Overview

The **Direction Stimulus Prompting** is a prompting method that helps guide an LLM’s output by giving it **explicit instructions or “directions” mid-task**, rather than just in the initial prompt.

Think of it as:

> “Let me stop the model for a second, give it a little nudge in the right direction, and then let it keep going.”

It’s usually implemented in **multi-turn reasoning** settings, where:

- The model tries to solve a complex problem.
    
- You insert **intermediate prompts** (the “stimulus”) that help the model reason better.
    
- These intermediate cues can “redirect” or “refocus” the model if it's starting to go off-track.

Let's say the model is solving a math word problem and gets stuck.

- **User (DSP):** “Focus only on identifying the known values from the question.”
    
- Then the model re-focuses on that sub-task.
    

You're not solving it all at once, you're **nudging** it step-by-step, like a tutor guiding a student.