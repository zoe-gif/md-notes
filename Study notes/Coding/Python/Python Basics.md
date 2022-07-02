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

### Setup

- [Python](https://www.python.org/)
- Editor: [Atom](https://atom.io/)
    - Try not to use Integrated Development Environment (IDE)
    - Atom: enter the path for a new file
        - filename.py
- Create directory

~~~
# create directory
mkdir dirname

# go to directory location
cd dirname

# check directory info
dir
~~~

- Run files in directory

~~~
python filename.py
~~~

### Hello world

- `print("hello world")` or `print('hello world')`
- `print("1 + 2 + 2 = ", 1 + 2 + 2, variable-name)`

### Comment

- `#comment`
- `""" multiline comment """`
- `#` in a string is not a comment

### Numbers and math

- +; -; *; /;% modulus; <; >; <=; >=

### Variables, String, Print

- f-string: `f"use {vairable} in a string"`
- `vairable = "now I'm using a {}"`
- `example_format.format(string)`
- `variable_full = variable_left + variable_right`
- `print("." * 10)`
- `print(""" multiple lines """)`
- `end = ' '`: to tell print to not end the line with a newline character and go to next line

### Escape Sequence

<img src="https://raw.githubusercontent.com/zoe-gif/images/master/20220630223226.png" width="600" height="">

### Get value

- `variable = input("prompt message")`
- Argument

~~~
from sys import argv
# Import argv from sys modules
# argv is the argument variable which holds the arguments you pass to script

script, first, second, third = argv
# Unpack argv and assign it to all varaibles in order

# Run it by giving arguments
python ex13.py first second third
~~~

### Use pydoc for help

- Install
- `python -m pydoc`

### Open and read file

- Example of open and read a file
~~~
from sys import argv

sript, filename = argv

txt = open(filename)

print(f"Here's your file {filename}:")
print(txt.read())

print("type the filename again:")
file_again = input("> ")

txt_again = open(file_again)

print(txt_again.read())
~~~

- `open(file, mod='r')`
    - `file` is file name
    - `mode` speficies te mode in which the file is opened
        - `r` - open for reading (default)
        - `w` - open for writing, wipe out all content
        - `x` - crate a new file and open for writing
        - `a` - open for writing, appending to the end of the file if it exits
- `close`: close the file
- `read`: read contents of the file
- `readline`: read just one line of a text file
    - Each time of `f.readline()` move to next `\n`
- `truncate`: wipe out specified content
- `write('stuff')`: write 'stuff' to the file
- `seek(0)`: move the read/write loction to the beginning of the file, by bytes
- `exits()`
    - `from os.path import exists`
    - Return true if an file exists
- `len()`: return length of string

### Function

- `def function_name(function_variable): function_statement`
- `*vairable` to take all the arguments to the function and put in variable as a list; like `argv`

