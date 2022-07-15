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
- Assignment operator
    - `=`, `+=`, `-=`, `*=`, `/=`, `%=`, `//=`, `**=`

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

- Arithmetic operator
    - `+`, `-`, `*`, `/`
    - `//` return integer for floor divisoin discarding any fractional result
    - `%` for reminder
    - `**` for powers
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
    - Check if characters in string `in` & `not in` (membership operator)
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

- `True` or `False`
- Comparison operator: `<`, `>`, `==`, `!=`, `<=`, `>=`
- Logical operator: `and`, `or`, `not`
- Identity operator: `is`, `is not`
- False values
    - `bool(None)`
    - `bool(0)`
    - `bool("")`
    - `bool(())`, `bool([])`, `bool({})`

#### List

- Might contain items of different types
- Ordered, changeable, allow duplicate
    - `test = list((1, 2, 3))`
    - `test = [1, 2, 3]`
- Index and slice
    - Same as string
        - Left index included, right index excluded
    - Can assign new value to slice
        - `test[:1] = []` --> `[3]`
        - `test[:] = []` --> `[]`
- `in` & `not in` to check membership
- `len()` return the number of items
- Unpacking into variable
    - Add `*` to a vairable, if the number of variables is less than value
        - `(a, b, *c) = thisList`
        - `c` is a list
- List comprehension
    - <code>newlist = [<i>expression</i> for <i>item</i> in <i>iterable</i> if </i>condition == True]</code>
    - `newlist = [x.upper() for x in oldlist if x != "apple"]`
- Loop through a list

~~~
# loop through a list
thislist = ["apple", "banana", "cherry"]
for x in thislist:
    print(x)
~~~

~~~
# list comprehension
thislist = ["apple", "banana", "cherry"]
[print(x) for x in thislist]
~~~

~~~
# loop through list index
thislist = ["apple", "banana", "cherry"]
for i in range(len(thislist)):
    print(thislist[i])
~~~

~~~
# loop through list index
thislist = ["apple", "banana", "cherry"]
i = 0
while i < len(this list):
    print(thislist[i])
    i += 1
~~~

- List method   
    - Insert item
        - `insert(index, insertContent)`
            - `test.insert(1, 0)` --> `[1, 0, 2, 3]`
    - Append item at the end
        - `append()`: append item
            - `for x in list2: list1.append(x)`
        - `extend()`: append items from another iterable object: 
            - Iterable object: list, typle, set, dictionary
            - `list1.extend(list2)`
        - `+`: `list3 = list1 + list2`
    - Remove item
        - `remove(value)`: remove item
        - `pop(index)`: remove by sepcified index
            - `pop()` --> remove the last item
    - Clear the list
        - `clear()` --> `[]`
    - Sort
        - `sort()`: sort alphanumerically
        - `sort(reverse  = True)`: sort reversely
        - `sort(key = myfunction)`: sort
            - `myfunction` return a number used to sort the list
            - Sort will be from the lowest to highest
            - e.g. `def myfunction(n): return abs(n - 50)`
                - `abs()`: absolute value
            - e.g. `thislist = sort(key = str.lower)`
        - Case sensitive: capital letters sorted before lower case letters
    - Reverse order of list
        - `reverse()`
    - Copy a list
        - `copy()`: `list2 = list1.copy()`
        - `list()`: `list2 = list(list1)`
        - `list1 * 2`
    - Count spec value in list
        - `count(value)`

#### Tuple

- Ordered, unchangeable, allow duplicate
    - `thisTuple = tuple(("a", "a", "b", True))`
    - `thisTuple = ("a",)` #need to have a comma to create one-item tuple
- Change tuple value by changing type to list

#### Set

- Unordered (unindexed), unchangeable (can remove or add items), no duplicate
    - `myset = set(("a", "b", 33.1))`
    - `myset = {"a", "b", 33.1}`
    - Duplicated item auto deleted/merged
- Set method
    - Add item
        - `add(value)`
    - Add any iterable
        - `update(mylist)`
    - Remove
        - `remove()`: if the item to remove not exist, `remove()` will raise ERROR
        - `discard()`: if the item to remove not exist, `discard()` will not raise ERROR
        - `pop()`: cannot spec index, can only remove the last item
        - `clear()`: empty set
        - `del()`: delete set completely
    - Join sets
        - `union(set2)`
        - `update(set2)`
    - Duplicates and differences
        - Keep duplicates
            - `set1.intersection_update(set2)`: keep duplicates and update `x`
            - `set3 = set1.intersection(set2)`: return a new set of duplicates
        - Keep all but duplicates
            - `set1.symmetric_difference_update(set2)`
            - `set3 = set1.symmetric_difference(set2)`
        - Items only exist in `set1` not `set2`
            - `set3 = set1.difference(set2)`
        - Whether two sets have a intersection or not
            - `isdisjoint()`
        - Whether `set2` is subset(part of)/superset(contain) `set1`
            - `set1.issubset(set2)`
            - `set1.issuperset(set1)`

#### Dictionary

- Ordered, changeable, no duplicate
    - Store data in key:value pairs
    - `thisdict = {"brand": "Cola", "year": 1998, "color": ["red, "yellow"]}`
- `in` & `not in`: check if key exists
- Dictionary method
    - Get from dict
        - Get value
            - `thisdict["owner"] = "John"`
            - `thisdict.get("owner")`
            - `values()`: get list of all values
        - Get list of all keys
            - `keys()`
        - Get items
            - `items()`: return each pair of item as tuple in a list
    - Update item
        - `update({"year": 2020})`: must in key:value pair
    - Remove item
        - `pop("year")`
        - `del thisdict["year"]`
        - `clear()`: to empty dict
    - Copy
        - Copy cannot by `dict1 = dict2` - just a reference that changes auto following `dict1`
        - `copy()`
    - Set default value of key
        - `setdefault("color" : "white")`
        - If the key not exists, inser the key with the specified value
    - Create dict by specified keys and value
        - `dict.formkeys(keys, value)`
        - `thisdict = dict.formkeys (x, y)`
            - If value not specified: `None`
- Nested dict
    - Dict can contain dict as item value

## Control flow tools

### `if` statement

- `if ... elif ... (else ...)`
    - `elif` stands for else if
- Short hand
    - `if a == b: print ("equal")`
    - `print("A") if a > b else print("<") if a <b else print("=")`
- `pass` statement
    - `if` statement cannot be empty, use `pass` if no content
- Nested if

### `while` statement

- `break` statement to stop the loop
- `continue` statement to stop the current iteration, and continue with the next iteration in loop
- `else` statement
- Nest while

### `for` statement

- For iterating over a sequence
    - List, tuple, set, dict, string
    - `for x in "test": print(x)`
- `break` statement
- `pass` statement
- `continue` statement
- `else` statement
- `range()` function
    - `range(start, end, increment)`
    - Return a sequance of number
    - Starting from 0 by default, increment by 1 by default
    - Include left, exclude right
    - `for x in range(0, 10, 3): print(x)` --> `4`
- Nested for

~~~

# Modify a collection by iterating
users = {'A': 'active', 'B': 'active', 'C': 'inactive'}

# Strategy: iterate over a copy
# items() return dict pairs in list
for user, status in users.copy()items():
    if status == 'inactive':
        del users[user]

# Strategy: create a new collection
active.users = {}
for user, status in users.items():
    if status == 'active':
        active.users[user] = status

~~~

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
- `del` keyword



