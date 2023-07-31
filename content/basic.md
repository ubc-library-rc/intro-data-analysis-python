---
layout: default
title: Basic Concepts and Commands
nav_order: 6
parent: Workshop Content
has_toc: false
---

## 1. Operators

In Python, basic operators are used to perform various operations on data, variables, and values. There are several types of operators, including:

{: .list-with-space}
* **Arithmetic Operators**: These operators are used to perform basic mathematical operations such as addition, subtraction, multiplication, and division. Examples include
	- Addition: `+`
    - Subtraction: `-`
    - Multiplication: `*`
    - Division: `/`
    - Floor Division: `//` (returns the quotient without the decimal part)
    - Modulo: `%` (returns the remainder of the division)
    - Exponentiation: `**`

* **Assignment Operators**: These operators are used to assign or update a value to a variable.
Examples include
    - Assignment: `=`
    - Add and assign: `+=`
    - Subtract and assign: `-=`

* **Comparison Operators**: These operators are used to compare two values or variables and return a logical value of TRUE or FALSE. Examples include
	- Equal to: `==`
    - Not equal to: `!=`
    - Greater than: `>`
    - Less than: `<`
    - Greater than or equal to: `>=`
    - Less than or equal to: `<=`

* **Logical Operators**: These operators are used to perform logical operations on values or variables, and return a logical value of TRUE or FALSE. Examples include
    - AND: `and` (returns True if both conditions are True)
    - OR: `or` (returns True if at least one condition is True)
    - NOT: `not` (returns the opposite Boolean value)

* **Membership Operators**:
    - `in` (used to check if a value is present in a sequence, like a list or a string)
    - `not in` (used to check if a value is not present in a sequence)

* **Identity Operators**:
    - `is` (used to check if two variables refer to the same object)
    - `is not` (used to check if two variables do not refer to the same object)

Understanding how to use these different types of operators is important for writing efficient and effective code in Python.

### Practice 1
Go to [Google Colab](https://colab.research.google.com/) to start a new notebook and try to compare the magnitude of the following numbers:
* the sum of all integers from 1 to 100,
* 10 to the power of 11,
* 11 to the power of 10.

<details>
<summary>Solution</summary>
a = (1 + 100) * 100 / 2 <br>
b = 10 ** 11 <br>
c = 11 ** 10 <br>
print(a < b) <br>
print(b < c) <br>
print(a < c) <br>
</details>

## 2. Functions

When we calculate the sum of all the integers from 1 to 100, we use a formula to help simplify the calculation. What if we cannot memorize the formula? Does it mean that we have to sum those integers brute force by typing 1 + 2 + 3 + ... all the way up to 100? We can use two built-in functions `sum()` and `range()`.

Input
{: .label .label-green}
```python
print(help(sum)) # get documentation for the sum function
print(help(range)) # get documentation for the range function

sum(range(1, 101)) # sum from 1 to 100
```

In Python, a **function** is a block of reusable code that performs a specific task or a set of tasks. Functions allow you to break down complex problems into smaller, more manageable pieces, making your code more organized, modular, and easier to maintain.

Functions in Python are defined using the `def` keyword, followed by the function name, a set of parentheses containing optional parameters, and a colon. The function body is indented under the function definition. Functions can have default values, and can return values using the return statement. Here's a simple example of a function that calculate the sum of numbers within the specified range :

Input
{: .label .label-green}
```python
# define the function
def sum_range(start, end, step=1):
    total_sum = 0
    current_number = start
    while current_number <= end:
        total_sum += current_number # total_sum = total_sum + current_number
        current_number += step # current_number = current_number + step
    return total_sum

# using the function
result = sum_range(1, 100)
print(result)  # Output: 5050 (sum of numbers from 1 to 100)

result_with_step = sum_range(2, 10, 2)
print(result_with_step)  # Output: 30 (sum of even numbers from 2 to 10)
```

When Python is installed, it comes with a variety of **built-in functions** that are readily available without having to write the code from scratch.  Here are some of the essential built-in functions:

| Function         | Description                                                                                                   |
| ---------------- | ------------------------------------------------------------------------------------------------------------- |
| `print()`        | Used to display output to the console.                                                                       |
| `len()`          | Returns the length of a sequence (e.g., string, list, tuple).                                                |
| `range()`        | Generates a sequence of numbers.                                                                             |
| `sum()`          | Calculates the sum of elements in a sequence.                                                                |
| `min()`, `max()` | Returns the minimum and maximum elements of a sequence.                                                      |
| `round()`        | Rounds a number to a specified precision.                                                                    |
| `type()`         | Returns the type of an object.                                                                               |
| `int()`, `float()`, `str()`, `bool()`, etc.    | Convert values to different data types.                                                                   |
| `input()`        | Reads input from the user through the console.                                                               |
| `open()`, `read()`, `write()`, `close()` | Used for file handling.                                                                                |

Using them effectively can significantly simplify and streamline your Python code.

## 3. Libraries

As introduced earlier, Python is powerful partially because its robust data libraries and extensive ecosystem.

A **Python library** is a collection of pre-written code and functions that extend the capabilities of the Python programming language. Libraries contain reusable modules that provide specific functionalities, making it easier to perform various tasks, focusing on solving specific problems or addressing specific domains.

When Python is installed, it comes with a set of default libraries known as the **Python Standard Library**. The Python Standard Library is included with every standard Python distribution, so you don't need to install anything separately to use these libraries. Here are some of the core modules from the Python Standard Library:

| Library          | Description                                                                                                                     |
| ---------------- | ------------------------------------------------------------------------------------------------------------------------------- |
| `math`           | Provides mathematical functions and constants.                                                                                  |
| `os`             | Offers operating system-related functionalities (e.g., file and directory operations).                                        |
| `sys`            | Accesses Python interpreter variables and functions.                                                                            |
| `datetime`       | Works with dates, times, and time intervals.                                                                                    |
| `random`         | Generates random numbers and performs random selections.                                                                        |
| `json`           | Deals with JSON (JavaScript Object Notation) data.                                                                              |
| `csv`            | Handles CSV (Comma-Separated Values) files.                                                                                     |
| `urllib`         | Helps with URL handling and HTTP requests.                                                                                      |
| `re`             | Implements regular expressions for pattern matching.                                                                            |
| `os.path`        | Provides additional functionality for file path manipulation.                                                                   |


These are just a few examples, and there are many more modules available in the Python Standard Library and beyond that, each serving different purposes. You can install **additional libraries** using package managers like `pip` (Python's package installer) and then `import` them into their Python scripts or interactive sessions.

### Practice 2
Go to your Google Colab notebook, insert new cells and try import the following libraries:

Input
{: .label .label-green}
```python
# import Numpy for numerical operations
import numpy as np

# try out the sort function from Numpy
# https://numpy.org/doc/stable/user/absolute_beginners.html
arr = np.array([2, 1, 5, 3, 7, 4, 6, 8])
np.sort(arr)
```

Input
{: .label .label-green}
```python
# import Pandas for managing datasets
import pandas as pd

# try out DataFrame function from pandas
# https://pandas.pydata.org/docs/getting_started/index.html#getting-started
df = pd.DataFrame(
    {
        "Name": [
            "Braund, Mr. Owen Harris",
            "Allen, Mr. William Henry",
            "Bonnell, Miss. Elizabeth",
        ],
        "Age": [22, 35, 58],
        "Sex": ["male", "male", "female"],
    }
)
df
```

Input
{: .label .label-green}
```python
# import Matplotlib and submodule for ploting and customization
import matplotlib as mpl
import matplotlib.pyplot as plt

# try out subplot function from pyplot
# https://matplotlib.org/stable/tutorials/introductory/quick_start.html#sphx-glr-tutorials-introductory-quick-start-py
fig, ax = plt.subplots()  # Create a figure containing a single axes.
ax.plot([1, 2, 3, 4], [1, 4, 2, 3])  # Plot some data on the axes.
```

## 4. Data Type and Data Structure

**Data Types**:
   Python supports several built-in data types, which define the type and behavior of data stored in variables. Some of the common data types in Python are:
   - Numeric Types: `int`, `float`, `complex`
   - Text Type: `str`
   - Boolean Type: `bool`
   - Sequence Types: `list`, `tuple`, `range`
   - Mapping Type: `dict`
   - Set Types: `set`, `frozenset`
   - None Type: `None`

**Data Structures**:
   Data structures in Python are collections that allow you to organize and manipulate data efficiently. Python provides several built-in data structures, including:
   - Lists: Ordered, mutable sequences represented using square brackets `[ ]`.
   - Tuples: Ordered, immutable sequences represented using parentheses `( )`.
   - Dictionaries: Unordered collections of key-value pairs represented using curly braces `{ }`.
   - Sets: Unordered collections of unique elements represented using curly braces `{ }`.
   - Strings: Sequences of characters represented using quotes, such as `"Hello"` or `'Python'`.
   - Arrays: Homogeneous collections of elements with a fixed size (available through the `array` module or `numpy` library).

These data types and data structures are versatile and allow you to handle various types of data in Python efficiently. By understanding how to use them effectively, you can write clean, concise, and powerful Python code for a wide range of applications.

In the next section, we will look into how to work with data frames, which is a popular data structure used in data analysis and manipulation, particularly in the context of data science and machine learning.

<br>
<p style="color:grey; font-size:14px; padding-top: 2em">
This page is meant to introduce basic concepts and commands in Python.<br>
What questions do you have about the terminologies and syntax? Now is a good time  to share your questions, thoughts and comments.
