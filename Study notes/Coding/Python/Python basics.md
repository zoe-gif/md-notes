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

## Control flow tools

## Data structures

## Modules

## Input and output

## Errors and exceptions

## Classes

## Standard library

## Virtual environments and packages