#programming #computing
# Python
#python 

The def keyword begins a function definition. Each function can have zero or more formal parameters in () parenthesis, followed by a : colon. Statements for the body of the function begin on the line following def and must be indented in a block.

```
# The body of a function is indented by 2 spaces, & prints the sum of the numbers.
def add_two_numbers(number_one, number_two):
  total = number_one + number_two
  print(total)  

>>> add_two_numbers(3, 4)
7


# Inconsistent indentation in your code blocks will raise an error.
>>> def add_three_numbers_misformatted(number_one, number_two, number_three):
...     result = number_one + number_two + number_three   # This was indented by 4 spaces.
...    print(result)     #this was only indented by 3 spaces
...
...
  File "<stdin>", line 3
    print(result)
    ^
IndentationError: unindent does not match any outer indentation level
```

Functions explicitly return a value or object via the `return` keyword:

# Function definition on first line, explicit return used on final line.
>>> def add_two_numbers(number_one, number_two):
        return number_one + number_two   


# Calling the function in the Python terminal returns the sum of the numbers.
>>> add_two_numbers(3, 4)
7

# Assigning the function call to a variable and printing it 
# will also return the value.
>>> sum_with_return = add_two_numbers(5, 6)
>>> print(sum_with_return)
11
Functions that do not have an explicit return expression will implicitly return the None object. This means that if you do not use return in a function, Python will return the None object for you. The details of None will be covered in a later exercise. For the purposes of this exercise and explanation, None is a placeholder that represents nothing, or null:

# This function does not have an explicit return.
def add_two_numbers(number_one, number_two):
  result = number_one + number_two


# Calling the function in the Python terminal appears 
# to not return anything at all.
>>> add_two_numbers(5, 7)
>>>


# Using print() with the function call shows that 
# the function is actually returning the **None** object.
>>> print(add_two_numbers(5, 7))
None


# Assigning the function call to a variable and printing 
# the variable will also show None.
>>> sum_without_return = add_two_numbers(5, 6)
>>> print(sum_without_return)
None
Calling Functions
Functions are called or invoked using their name followed by (). Dot (.) notation is used for calling functions defined inside a class or module.

>>> def number_to_the_power_of(number_one, number_two):
        return number_one ** number_two
...

>>> number_to_the_power_of(3,3) # Invoking the function with the arguments 3 and 3.
27


# A mismatch between the number of parameters and the number of arguments will raise an error.
>>> number_to_the_power_of(4,)
...
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: number_to_the_power_of() missing 1 required positional argument: 'number_two'


# Calling methods or functions in classes and modules.
>>> start_text = "my silly sentence for examples."
>>> str.upper(start_text)  # Calling the upper() method for the built-in str class.
"MY SILLY SENTENCE FOR EXAMPLES."

# Importing the math module
import math

>>> math.pow(2,4)  # Calling the pow() function from the math module
>>> 16.0
