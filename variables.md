---
title: Variables & Data types
category: Variables
layout: post
---
> [Strings](./strings.html) || [Variables](./variables.html) || [Lists](./lists.html) || [Tuples](./tuples.html) || [Dictionary](./dictionary.html) ||
>  [Control](./control.html) || [Function](./function.html)|| [Files](./files.html) || [OOP](./oop.html) ||

***    

### Assignment - Value
- Process of storing a value inside a variable is called assignment.
- Every variable is connected to a value. 
- The assignment operator (“=” symbol) is assigning value(s) to a variable.

```python
    variablename = value(s)
```
Variable Naming Restrictions
- no keywords
- No spaces
- Start with letter of underscores
- Only letters, numbers and underscore
- Case sensitive
    - lowercase, 
    - contain only letters, numbers, and underscores,
    - short and descriptive.

#### Examples

```python
        message = "This is a message."
        print(message)
# OUTPUT
# This is a message.
```

```python
# Multiple assignment
    x,y,z = 1,2,3
```
* Data Types

```python
print(type("a")
<class 'str'>
print(type(2)
<class 'int'>
print(type(2.5)
<class 'float'>
```

#### Expression
- is a combination of numbers, symbols or other variables that produce a result when evaluated.


### CASTING Implicit vs Explicit Conversion
#### Implicit conversion 
is where the interpreter helps us out and automatically converts one data type into another, without having to explicitly tell it to do so.
#### Explicit conversion
is where we manually convert from one data type to another by calling the relevant function for the data type we want to convert to.
```python
print("2 + 2 = " + str(2 + 2))
```
we needed to call the str() function to convert the number into a string. 
```python
Base = 6
Height = 3
Area = (base*height)/2
print(“the area of the triangle is: “ + str(area))
```
#### Print methods
```python
first_name = "Mike"
last_name = "O'Neill"
full_name = f"{first_name} {last_name}"
print(full_name.title())
# OUTPUT
# 
```
##### f-string 
```python
full_name = f"{first_name} {last_name}"
print(full_name.upper())
print(full_name.lower())
# OUTPUT
# 
```
##### more methos
```python
first_name = "Mike"
last_name = "O'Neill"
full_name = f"{first_name} {last_name}"
print(f"Hello, {full_name.title()}!")
# OUTPUT
# 
```
or
```python
first_name = "Mike"
last_name = "O'Neill"
message = f"Hello, {full_name.title()}!"
print(message)
# OUTPUT
# 
```
or
```python
first_name = "Mike"
last_name = "O'Neill"
full_name = "{} {}".format(first_name, last_name)
print(full_name)
# OUTPUT
# 
```
### Whitespace, Tabs and Newlines
```python
print("Python")
print("\tPython")
print("Languages:\nC++\Java\nbash\tPython")

# OUTPUT
# Python
```
#### String methods

| **Method**      | **Description** | 
| :---        | :----   | 
| casefold() | Converts string into lower case       |
| capitalize() | Converts string into capitalized case       |
| center() | Returns a centered string       |
| count() | Returns the number of times a specified value occurs in a string  |
| encode() | Returns an encoded version of the string |
| endswith() | Returns true if the string ends with the specified value |
| expandtabs()      | Sets the tab size of the string |
| find()      | Searches the string for a specified value and returns the position of where it was found |
| format()      |  Formats specified values in a string |
| format_map() | Formats specified values in a string  |
| index() | Searches the string for a specified value and returns the position of where it was found |
| isalnum() | Returns True if all characters in the string are alphanumeric   |
| isalpha() | Returns True if all characters in the string are in the alphabet  |
| isdecimal() | Returns True if all characters in the string are decimals  |
| isdigit()      | Returns True if all characters in the string are digits |
| isidentifier()      | Returns True if the string is an identifier |
| islower() | Returns True if all characters in the string are lower case   |
| isnumeric() | Returns True if all characters in the string are numeric  |
| isprintable() | Returns True if all characters in the string are printable  |
| isspace()      | Returns True if all characters in the string are whitespaces |
| istitle()      | Returns True if the string follows the rules of a title |
| isupper() | Returns True if all characters in the string are upper case   |
| join() | Joins the elements of an iterable to the end of the string  |
| ljust() | Returns a left justified version of the string  |
| lower()      | Converts a string into lower case |
| lstrip()      | Returns a left trim version of the string |
| maketrans() | Returns a translation table to be used in translations   |
| partition() | Returns a tuple where the string is parted into three parts  |
| replace() | Returns a string where a specified value is replaced with a specified value  |
| rfind()      | Searches the string for a specified value and returns the last position of where it was found  |
| rindex() | Searches the string for a specified value and returns the last position of where it was found   |
| rjust() | Returns a right justified version of the string  |
| rpartition() | Returns a tuple where the string is parted into three parts  |
| rsplit()      | Splits the string at the specified separator, and returns a list  |
| rstrip()      | Returns a right trim version of the string  |
| split() | Splits the string at the specified separator, and returns a list   |
| splitlines() | Splits the string at line breaks and returns a list  |
| startswith() | Returns true if the string starts with the specified value  |
| strip()      | Returns a trimmed version of the string  |
| swapcase()      | Swaps cases, lower case becomes upper case and vice versa  |
| title() | Converts the first character of each word to upper case   |
| translate() | Returns a translated string  |
| zfill() | Fills the string with a specified number of 0 values at the beginning  |