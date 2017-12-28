## General Intro

> The single most important skill for a computer scientist is **problem solving**. Problem solving means the ability to formulate problems, think creatively about solutions, and express a solution clearly and accurately

An **algorithm **is a step by step list of instructions that if followed exactly will solve the problem under consideration.

### Programming languages

#### Low-level languages \(aka. machine languages\)

Machine language is the encoding of instructions in binary so that they can be directly executed by the computer. Assembly language uses a slightly easier format to refer to the low level instructions. Loosely speaking, computers can only execute programs written in low-level languages. To be exact, computers can actually only execute programs written in machine language.

#### High-level languages

Thus, programs written in a high-level language \(and even those in assembly language\) have to be processed before they can run. This extra processing takes some time, which is a small disadvantage of high-level languages.

* It is much easier to program in high-level languages
* igh-level languages are portable, meaning that they can run on different kinds of computers with few or no modifications

#### Translating high- to low-level

* interpreters - line by line
* compilers - turns high-level source code into low-level object code AKA. executable.

_Many modern languages use both processes_. They are first **compiled** into a lower level language, called byte code, and **then interpreted** by a program called a virtual machine. Python uses both processes, but because of the way programmers interact with it, it is usually considered an interpreted language.

### Python high- or low- ???

Python is compiled on the fly.

### Comments

```python
# Usual comments in Python

#---------------------------------------------------
# This is often at the beginning of programs
# It usually says what the progr is about
# and who made it, etc
#---------------------------------------------------
'''
docstring comments and multi-line comments
'''
```

### Python shell

Python REPL can be used in terminal via:

* `python` or `python3` depending on installation
* `exit()`
* `quit()`

Or in IDLE that comes with python. 

### Python help

In REPL / Shell:

```python
help()
Welcome to Python 3.6's help utility!

If this is your first time using Python, you should definitely check out
the tutorial on the Internet at http://docs.python.org/3.6/tutorial/.

Enter the name of any module, keyword, or topic to get help on writing
Python programs and using Python modules.  To quit this help utility and
return to the interpreter, just type "quit".

To get a list of available modules, keywords, symbols, or topics, type
"modules", "keywords", "symbols", or "topics".  Each module also comes
with a one-line summary of what it does; to list the modules whose name
or summary contain a given string such as "spam", type "modules spam".

help> 
You are now leaving help and returning to the Python interpreter.
If you want to ask for help on a particular object directly from the
interpreter, you can type "help(object)".  Executing "help('string')"
has the same effect as typing a particular string at the help> prompt.
>>> help(str)
>>> help(str.__add__)
"""
__add__(self, value, /)
    Return self+value.
(END)
"""

# press q to exit long text
```

### Python from files

1. make a file `this_is_my_file.py`
2. put code in it
3. run from terminal: `python this_is_my_file.py`

