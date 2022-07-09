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

- Comment
    - `#` for single line
    - `''' ... '''` for multiple lines
- Number
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
- String
    - In single or double quotes <code>\`...\`</code> or <code>"..."</code>
    - Escape special character with balckslash
        - `\'` --> `'`
        - `\\` --> `\`
        - `\n` --> new line
        - `\r` --> carriage return
        - `\t` --> tab
        - `\b` --> backspace
    - Concat string
        - Concatenate string with `+`, repeat with `*`
            - `3 * 'm' + 'os'` --> `mmmos`
        - Auto concatenate for two or more string literals enclosed between quotes
            - `'py' 'th' 'on'` --> `python`
    - String index
        - First character having index 0
        - Indices can be negative, counting from the right from -1
        - `'python'[1]'` --> `y`; `'python'[-1]` --> `n`
        - 000000000000000000000000000000000000000000000

- `print()` function
    - `print('Hello world.\nI'm back.')`
    - `print(8 + 8)`
    - <code>print(<i>variable</i>)</code>
    - Add `r` to use raw string instead of interpreting special characters by `\`
        - `print('C:\some\location')`
    - Multiple lines by `''' ... '''` or `""" ... """`

## Control flow tools

## Data structures

## Modules

## Input and output

## Errors and exceptions

## Classes

## Standard library

## Virtual environments and packages