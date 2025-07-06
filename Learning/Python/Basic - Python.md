Python is a dynamic and strongly typed programming language. It employs both duck typing and gradual typing via type hints.

While Python supports many different programming styles, internally everything in Python is an object. This includes numbers, strings, lists, and even functions.

We'll dig more into what all of that means as we continue through the track.

This first exercise introduces 4 major Python language features:

Name Assignment (variables and constants),
Functions (the def keyword and the return keyword),
Comments, and
Docstrings.

 ``` markdown
***Note***
In general, content, tests, and analyzer tooling for the Python track follow the style conventions outlined in PEP 8 and PEP 257 for Python code style, with the additional (strong) suggestion that there be no single letter variable names.

On the Python track, variables are always written in snake_case, and constants in SCREAMING_SNAKE_CASE.
```


Comments
Comments in Python start with a # that is not part of a string, and end at line termination. Unlike many other programming languages, Python does not support multi-line comment marks. Each line of a comment block must start with the # character.

Docstrings
The first statement of a function body can optionally be a docstring, which concisely summarizes the function or object's purpose. Docstrings are declared using triple double quotes (""") indented at the same level as the code block:


# An example from PEP257 of a multi-line docstring.
def complex(real=0.0, imag=0.0):
    """Form a complex number.

    Keyword arguments:
    real -- the real part (default 0.0)
    imag -- the imaginary part (default 0.0)
    """

    if imag == 0.0 and real == 0.0:
        return complex_zero

Docstrings are read by automated documentation tools and are returned by calling the special attribute .__doc__ on the function, method, or class name. Docstring conventions are laid out in PEP257.

Docstrings can also function as lightweight unit tests, which will be covered in a later exercise.

# An example on a user-defined function.
>>> def number_to_the_power_of(number_one, number_two):
        """Raise a number to an arbitrary power.

        :param number_one: int the base number.
        :param number_two: int the power to raise the base number to.
        :return: int - number raised to power of second number

        Takes number_one and raises it to the power of number_two, returning the result.
        """

        return number_one ** number_two
...

# Calling the .__doc__ attribute of the function and printing the result.
>>> print(number_to_the_power_of.__doc__)
Raise a number to an arbitrary power.

    :param number_one: int the base number.
    :param number_two: int the power to raise the base number to.
    :return: int - number raised to power of second number

    Takes number_one and raises it to the power of number_two, returning the result.