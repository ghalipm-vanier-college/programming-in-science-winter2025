# Lecture 3: Built-in Functions

### **Table of Contents**

1. [Python Built-In Functions, Packages, and Modules](#python-built-in-functions-packages-and-modules)
2. [Keep It Simple, Stupid (KISS)](#keep-it-simple-stupid-kiss)
3. [Open/Closed Principle](#open-closed-principle)
4. [Using Trigonometric, Logarithmic, and Exponential Functions](#using-trigonometric-logarithmic-and-exponential-functions)
5. [Comments in Python](#comments-in-python)
6. [Identifying and Fixing Common Errors Using Debugging Techniques](#identifying-and-fixing-common-errors-using-debugging-techniques)


### 1. **Python Built-In Functions, Packages, and Modules**

In Python, **built-in functions**, **packages**, and **modules** are essential tools that make development easier and more efficient. They provide predefined functionality that helps solve common problems.

- **Built-In Functions**: These are functions that Python provides by default, which can be used without any extra setup. Some common built-in functions include:
  - `print()`: Displays output to the user.
  - `len()`: Returns the length of an object (e.g., a string or list).
  - `int()`, `float()`, `str()`: Convert values between different data types.

Example:
```python
name = "Alice"
length = len(name)  # Using the built-in len() function to find the length of the string
print(length)  # Output: 5
```

- **Packages**: A package is a collection of related modules bundled together. You can install packages using Python’s package manager, `pip`, which provides additional functionality beyond the built-in features.

Example:
```python
# To use the math package, you must first import it
import math

# Now you can access all the functions in the math module, like sqrt()
result = math.sqrt(16)  # Result is 4.0
```

- **Modules**: A module is a single file that contains functions, classes, and variables that you can import into your program to reuse. For example, the `math` module provides functions for mathematical operations.

### 2. **Keep It Simple, Stupid (KISS)**

The **KISS principle** emphasizes keeping solutions simple and straightforward. In programming, this means writing code that is easy to read, understand, and maintain. Avoid overcomplicating problems or adding unnecessary complexity.

Key takeaways:
- **Write simple code**: Focus on clarity and simplicity instead of trying to make the code overly efficient or complex.
- **Use existing tools**: Leverage built-in functions, packages, and modules rather than reinventing the wheel.

Example (KISS principle):
Instead of writing a complex loop to find the maximum value in a list, use Python's built-in `max()` function:
```python
numbers = [1, 2, 3, 4, 5]
max_value = max(numbers)  # Simple and efficient way to get the max value
print(max_value)  # Output: 5
```

### 3. **Open/Closed Principle**

The **Open/Closed Principle** is part of object-oriented programming and suggests that software entities should be **open for extension**, but **closed for modification**. However, since the students have not yet learned about functions or classes, we will reframe this principle in a more general, non-object-oriented context.

In simple terms, the Open/Closed Principle means that you should design your code in such a way that you can **add new functionality without changing existing code**. This can be achieved by writing code that is modular and easy to extend.

Key takeaway:
- **Write code that can be easily extended**: Rather than modifying existing code to add new features, aim to extend your solution through simple adjustments and additions.

Example:
Let’s say you have a program that calculates the total cost of items in a shopping cart. Initially, you have a function to calculate the total without considering discounts:

```python
# Initial code: Calculate total cost
def calculate_total(cart):
    total = 0
    for item in cart:
        total += item['price']
    return total
```

Now, you want to add a discount feature. Instead of modifying the original function, you can extend it by adding new code without changing the existing one:

```python
# Extended code: Calculate total cost with discount
def calculate_total_with_discount(cart, discount=0):
    total = 0
    for item in cart:
        total += item['price']
    total_after_discount = total - (total * discount)
    return total_after_discount
```

In this example, you can calculate the total cost both with and without discounts, **extending** the functionality without modifying the original `calculate_total()` function.

### 4. **Using Trigonometric, Logarithmic, and Exponential Functions from the Python Math Library**

Python’s **math library** provides a wide range of mathematical functions, including trigonometric, logarithmic, and exponential operations. These functions help solve various problems in science and engineering.

Common functions in the `math` module:
- **Trigonometric Functions**: `sin()`, `cos()`, `tan()`, `asin()`, `acos()`, `atan()`
- **Logarithmic Functions**: `log()`, `log10()`, `log2()`
- **Exponential Function**: `exp()`

Example of using the **math** module:
```python
import math

# Trigonometric example: sine of 30 degrees
angle_radians = math.radians(30)  # Convert degrees to radians
sine_value = math.sin(angle_radians)
print("Sine of 30 degrees:", sine_value)  # Output: 0.49999999999999994

# Logarithmic example: natural log of 10
log_value = math.log(10)
print("Log of 10:", log_value)  # Output: 2.302585092994046

# Exponential example: e raised to the power of 2
exp_value = math.exp(2)
print("Exponential of 2:", exp_value)  # Output: 7.3890560989306495
```

These functions are useful for scientific applications that involve angles, logarithms, or growth models (such as in physics, biology, and economics).

### 5. **Comments in Python**

**Comments** in Python are lines of text that are ignored by the interpreter. They are used to explain and document code, making it easier to understand for other developers (or your future self).

- **Single-line comments** are created by adding a `#` before the comment.
- **Multi-line comments** can be created using triple quotes (`'''` or `"""`), though these are generally used for docstrings (documentation strings).

Example of single-line and multi-line comments:
```python
# This is a single-line comment

# Function to calculate speed
def calculate_speed(distance, time):
    '''This function calculates speed based on distance and time.'''
    speed = distance / time  # Speed calculation
    return speed

# Call the function
print(calculate_speed(100, 20))  # Output: 5.0
```

Comments are essential for maintaining and understanding code, especially when the program becomes more complex.

### 6. **Identifying and Fixing Common Errors Using Debugging Techniques**

**Debugging** is an essential skill in programming that involves identifying and fixing errors in code. Common errors in Python include **syntax errors**, **runtime errors**, and **logical errors**.

#### Common Debugging Techniques:
1. **Read error messages carefully**: Python provides useful error messages that tell you where the problem is in your code. Always read these messages to understand what went wrong.
2. **Use print statements**: Print the values of variables or the result of expressions to help understand what the program is doing at different points.
3. **Check for common mistakes**:
   - Missing or extra parentheses
   - Typographical errors in variable or function names
   - Incorrect indentation (Python relies on indentation to define code blocks)

Example of debugging with print statements:
```python
# Debugging an example of calculating speed
distance = float(input("Enter distance: "))
time = float(input("Enter time: "))

# Debugging: Check the inputs before calculating
print("Distance entered:", distance)
print("Time entered:", time)

# Perform calculation
speed = distance / time

# Output the result
print(f"Speed is {speed} meters per second.")
```

In this example, **print statements** are used to check if the inputs are correct before performing the calculation. This helps identify if the problem lies with the inputs or the calculation itself.
