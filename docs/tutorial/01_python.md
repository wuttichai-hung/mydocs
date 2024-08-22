# Basic Python

Welcome to this Basic Python Tutorial! This guide is designed to introduce you to the fundamental concepts of Python programming. Whether you're new to programming or coming from another language, this tutorial will help you get started with Python.

## 1. Introduction to Python

Python is a high-level, interpreted programming language known for its simplicity and readability. It's widely used in various fields, including web development, data science, artificial intelligence, and more.

Key features of Python:
- Easy to learn and read
- Extensive standard library
- Large and active community
- Cross-platform compatibility

## 2. Setting Up Your Environment

To start programming in Python, you need to set up your development environment:

1. Download and install Python from the [official website](https://www.python.org/downloads/).
2. Choose an Integrated Development Environment (IDE) or text editor. Popular choices include:
   - PyCharm
   - Visual Studio Code
   - IDLE (comes with Python installation)

After installation, you can run Python from the command line or your chosen IDE.

## 3. Basic Syntax

Python uses indentation to define code blocks. Here's a simple example:

```python
if True:
    print("This is indented")
print("This is not indented")
```

- Use 4 spaces for indentation (preferred over tabs)
- Lines shouldn't be longer than 79 characters
- Use blank lines to separate functions and classes

## 4. Variables and Data Types

Python is dynamically typed, meaning you don't need to declare variable types explicitly.

```python
# Integer
x = 5

# Float
y = 3.14

# String
name = "Python"

# Boolean
is_fun = True

# List
my_list = [1, 2, 3]

# Dictionary
my_dict = {"key": "value"}
```

## 5. Operators

Python supports various operators:

- Arithmetic: `+`, `-`, `*`, `/`, `//` (floor division), `%` (modulo), `**` (exponent)
- Comparison: `==`, `!=`, `<`, `>`, `<=`, `>=`
- Logical: `and`, `or`, `not`
- Assignment: `=`, `+=`, `-=`, `*=`, `/=`, etc.

Example:
```python
x = 10
y = 3

print(x + y)  # 13
print(x > y)  # True
print(x and y)  # 3
```

## 6. Control Flow

### If-Else Statements

```python
x = 10
if x > 5:
    print("x is greater than 5")
elif x == 5:
    print("x is equal to 5")
else:
    print("x is less than 5")
```

### Loops

For loop:
```python
for i in range(5):
    print(i)
```

While loop:
```python
count = 0
while count < 5:
    print(count)
    count += 1
```

## 7. Functions

Functions are defined using the `def` keyword:

```python
def greet(name):
    return f"Hello, {name}!"

print(greet("Python"))  # Output: Hello, Python!
```

## 8. Data Structures

### Lists

```python
fruits = ["apple", "banana", "cherry"]
fruits.append("date")
print(fruits[0])  # apple
```

### Dictionaries

```python
person = {
    "name": "John",
    "age": 30,
    "city": "New York"
}
print(person["name"])  # John
```

### Tuples

```python
coordinates = (10, 20)
print(coordinates[0])  # 10
```

## 9. Modules and Packages

Python has a vast standard library and many third-party packages. You can import modules using the `import` keyword:

```python
import math
print(math.pi)  # 3.141592653589793

from datetime import datetime
print(datetime.now())
```

## 10. File Handling

Reading from a file:
```python
with open("example.txt", "r") as file:
    content = file.read()
    print(content)
```

Writing to a file:
```python
with open("example.txt", "w") as file:
    file.write("Hello, Python!")
```

## 11. Error Handling

Use try-except blocks to handle errors:

```python
try:
    result = 10 / 0
except ZeroDivisionError:
    print("Error: Division by zero!")
```

## 12. Next Steps

After mastering these basics, you can explore:

- Object-Oriented Programming
- Web development with frameworks like Django or Flask
- Data analysis with libraries like Pandas and NumPy
- Machine Learning with scikit-learn and TensorFlow

Remember, practice is key to improving your Python skills. Try to work on small projects and solve coding challenges regularly.

Happy coding with Python!
