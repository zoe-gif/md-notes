---
title: Python Basics
date: 2022-06-10
update: 2022-06-20
categories:
- Study notes
- Coding
tags: Python
description: 
---

## Setup

- [Python](https://www.python.org/)
- Editor: [Atom](https://atom.io/)
    - Try not to use Integrated Development Environment (IDE)
    - Atom: enter the path for a new file
        - filename.py
- Create directory

## Features of Python

- Interpreted language
    - Source code not directly translated by the target machine
- Compact and readable
    - High-level data type
    - Statement grouping by indentation
    - No variable or argument declarations necessary
- Extensible

## Using Python interpreter

### Invoking interpreter

- `python` command in shell
- Exit: `Ctrl + Z` or `quit()`
- or <code>python -c <i>command</i> [arg] ...</code> to execute the statement in command
- <code>python -m <i>module</i> [arg] ...</code> to execute the source fiel for module
- `-i` before script to run script and enter interactive mode afterwards

### Argument passing

- Interpreter turn the scripte name and additional arguments into a list of strings, and assign to `argv` variable in `sys` module
- `import sys` in script to use `argv` variable
- Length of the list is at least one
    - `sys.argv[0]` is empty string, if no script and no arguments are given
    - `sys.argv[0]` is set to `-` (standard input), if script name is given as `-`
    - `sys.argv[0]` is set to `-c`, if `-c` commant is used
    - `sys.argv[0]` is set to the full name of the module, if `-m` module is used
- Options after `-c command` or `-m module` left in `sys.argv` for the command or module to handle, not by interpreter's option processing

### Interactive mode

- `>>>` primary prompt for the next command
- `...` secondary prompt for continuation lines

### Interpreter and environment

- Defualt encode in UTF-8
- Declare an encoding other than default, at first line:
    - <code>-\*- coding: <i>encoding</i> -\*-</code>
    - <code><i>encoding</i></code> is [codec](https://docs.python.org/3/library/codecs.html#module-codecs) registry and base classes

## Basics

### Comment

- `#` for single line
- `''' ... '''` for multiple lines

### Variable

- Variable casting
    - `str()`
    - `int()`
    - `float()`
- Variable name
    - Case sensitive
    - Naming format
        - Camel case `myVariableName`
        - Pascal case `MyVariableName`
        - Snake case `my_variable_name`
- Assign value to variables
    - `x, y = 3, "test"`
    - `x = y = "test"`
    - Unpack a collection of a value in list or tuple
        - `test = [1, 2]`
        - `x, y = test`
- Global and local variable
    - Global variable
        - Created outside a function
        - `global` keyword, created inside a function
    - Local variable
        - Created inside a function

### `print()` function
- `print('Hello world.\nI'm back.')`
- `print('8' + '+ 8 =', 8 + 8)`
- <code>print(<i>variable</i>)</code>
- Add `r` to use raw string instead of interpreting special characters by `\`
    - `print('C:\some\location')`
- Multiple lines by `''' ... '''` or `""" ... """`

### Data type

- Text type: `str`
- Numeric type: `int`, `float`, `complex`
- Sequence type: `list`, `tuple`, `range`
- Mapping type: `dict`
- Set type: `set`, `frozenset`
- Boolean type: `bool`
- Binary type: `bytes`, `bytearray`, `memoryview`
- None type: `NoneType`
- `type()` to get data type

#### Number

- Operator: `+`, `-`, `*`, `/`
- `//` return integer for floor divisoin discarding any fractional result
- `%` for reminder
- `**` for powers
- `=` to assign a vlaue to a variable
- Numeric type
    - `int`
    - `float`: division always return floating point nunmber
    - `complex`: `j` for imaginary part of complex number
- `_`
    - In interactive mode, the last printed expression is assigned to the variable `_`
- Random number
    - `import random` - built-in module
    - `random.randrage(1, 10)`

#### String

- In single or double quotes <code>\`...\`</code> or <code>"..."</code>
- Multiline string `"""..."""`
- Escape special character with balckslash
    - `\'` --> `'`
    - `\\` --> `\`
    - `\n` --> new line
    - `\r` --> carriage return
    - `\t` --> tab
    - `\b` --> backspace
- Concatenation
    - Concatenate string with `+`, repeat with `*`
        - `3 * 'm' + 'os'` --> `"mmmos"`
    - Auto concatenate for two or more string literals enclosed between quotes
        - `'py' 'th' 'on'` --> `"python"`
- Index and slice
    - String is array
    - First character having index 0
    - Indices can be negative, counting from the right from -1
        - `'python'[1]` --> `"y"`; `'python'[-1]` --> `"n"`
        - `'python'[0:2]` --> `"py"` (include position 0, exclude position 2)
        - `'python'[:2] + 'python'[2:]` --> `"python"`
        - `'python'[:]` --> `"python"`
    - Out of range index
        - Error for get the character of index
        - Ok for slicing
    - String is immutable, cannot assign value to an indexed position
    - Loop through a string
        - `for x in "banana": print(x)`
    - Check if characters in string `in` & `not in`
        - `"ba" in "banana"` --> `True`
        - `"ya" not in "banana"` --> `True`
- `len()`: return length of a string
- Format
    - Formatted string literal (f-string)
        - Prefixed with `f`, replacement fields `{}`
            - <code>f'Hello, my name is {<i>name</i>.lower()}'</code>
            - `f"1 + (1 - 2) = {1 + (1 - 2)}"`
            - `f'''He\'ll say {"I'm Eric"}'''` --> `"He'll say I'm Eric"`
        - `=` can be added after expression, casues `repr()` by default
            - `foo = "bar"`
            - `f"{ foo = }"` --> `" foo = 'bar'" 
        - Specify conversion
            - `!s` calls `str()` on the result
            - `!r` calls `repr()` on the result
            - `!a` called `ascii()` on the result
        - Format specifier `:`
            - Alignment
                - `:<` - left
                - `:>` - right
                - `:^` - center
                - `:=` - place sign to the left most position
                - Add int afterwards to spec available space for the value
            - Sign
                - `:+` - show + sign
                - `:-` - show - sign only
                - `: ` - use a space before positive number
            - Separator
                - `:,` - comma as thousand separator
                - `:_` - underscre as thousand separator
            - Number format
                - `:b` - binary format
                - `:c` - convert to unicode character
                - `:d` - decimal format
                - `:e` - scientific format with lower case e
                - `:E` - scientific format with upper case E
                - `:.2f` - fix point number format --> `5.00`
                - `:o` - octal format
                - `:x` - hex format
                - `:.0%` - percentage format --> `5%`
    - `str.format()`
        - `full_name = "{} {}".format(first_name, last_name)`
    - printf-style string formatting
        - `%`: string formatting or interpolation operator
        - `%(language)s has %(number)03d quote types' % {"language": "python", "number": 2}` --> `"pyhon has 002 quote types"`
            - `(language)`: mapping key, optional
            - `0`: conversion flag, optional
                - <img src="https://raw.githubusercontent.com/zoe-gif/images/master/20220710235621.png" width="600" height="">
            - `3`: minimum field width, optional
            - Precision `.2`, optional
            - Length modifier, optional
            - `d`: conversion type
                - <img src="https://raw.githubusercontent.com/zoe-gif/images/master/20220711000041.png" width="600" height="">
- [String method](https://docs.python.org/3/library/stdtypes.html#string-methods)
    - Case
        - `upper()` & `lower()` & `capitalize`
    - Remove whitespace
        - `strip()`
    - Replace character
        - `"abcd".replace("ab", "cd")` --> `"cdcd"`
    - Split
        - `"ad cd".split(" ")` --> `["ab", "cd"]`
    - Join
        - `join()`
    - Count
        - `count()`
    - End with
        - `endswith()`
    - Find position
        - `find()` & `index()`: return first position
        - `rfind()` & `rindex()`: return last position
    - Check type & format
        - `isalnum()`: if all are alphanumeric, alphabet or number
        - `isaloha()`: if all are alphabet
        - `isdecimal()`, `isnumeric()`, `isdigit()`, `isidentifier()`
        - `islower()`, `istitle()`, `isupper()`, `isspace()`
    - Fill 0 at the beginneing
        - `"90".zfill(4)` --> `0090`

#### Bollean

- 

#### List

- Might contain items of different types
    - `test = [1, 2, 3]`
- Mutable, item can be changed
- Index and slice
    - Same as string
    - Can assign new value to slice
        - `test[:1] = []` --> `[3]`
        - `test[:] = []` --> `[]`
- Concatenation and append
    - `+` to concatenate list
        - `test + [4, 5]` --> `[1, 2, 3, 4, 5]`
    - `append()` to add new item at the end
        - `test.append([4, 5])` --> `[1, 2, 3, [4, 5]]`
- `len()` return the number of items

## Control flow tools

### `if` statement

- 

### `while` statement

### `for` statement

- 

### `range()` function

- 


## Data structures

## Modules

## Input and output

## Errors and exceptions

## Classes

## Standard library

## Virtual environments and packages


## Uncategorized


- `eval()`: if the expression is legal python statement, it will be executed
- `repr`()`: return a string containing a printable representation of an object
- `lambda`
    - A small anonymous function, can take any number of arguments, but only one expression
    - `x = lambda a , b : a * b + 10`

