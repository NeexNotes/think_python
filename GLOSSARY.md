# Glossary 

# activecode

A unique interpreter environment that allows Python to be executed from within a web browser.

# algorithm

A general step by step process for solving a problem.

# bug

An error in a program.

# byte code

An intermediate language between source code and object code. Many modern languages first compile source code into byte code and then interpret the byte code with a program called a virtual machine.

# codelens

An interactive environment that allows the user to control the step by step execution of a Python program

# comment

Information in a program that is meant for other programmers \(or anyone reading the source code\) and has no effect on the execution of the program.

# compile

To translate a program written in a high-level language into a low-level language all at once, in preparation for later execution.

# conditional execution

Check for certain conditions and execute the appropriate sequence of statements

# debugging

The process of finding and removing any of the three kinds of programming errors.

# exception

Another name for a runtime error.

# executable

Another name for object code that is ready to be executed.

# formal language

Any one of the languages that people have designed for specific purposes, such as representing mathematical ideas or computer programs; all programming languages are formal languages.

# high-level language

A programming language like Python that is designed to be easy for humans to read and write.

# input

Get data from the keyboard, a file, or some other device.

# interpret

To execute a program in a high-level language by translating it one line at a time.

# low-level language

A programming language that is designed to be easy for a computer to execute; also called machine language or assembly language.

# math and logic

Perform basic mathematical operations like addition and multiplication and logical operations like`and`, `or`, and`not`.

# natural language

Any one of the languages that people speak that evolved naturally.

# object code

The output of the compiler after it translates the program.

# output

Display data on the screen or send data to a file or other device.

# parse

To examine a program and analyze the syntactic structure.

# portability

A property of a program that can run on more than one kind of computer.

# print function

A function used in a program or script that causes the Python interpreter to display a value on its **output device.**

# problem solving

The process of formulating a problem, finding a solution, and expressing the solution.

# program

A sequence of instructions that specifies to a computer actions and computations to be performed.

# programming language

A formal notation for representing solutions.

# Python shell

An interactive user interface to the Python interpreter. The user of a Python shell types commands at the prompt \(&gt;&gt;&gt;\), and presses the return key to send these commands immediately to the interpreter for processing.

# repetition

Perform some action repeatedly, usually with some variation.

# runtime error

An error that does not occur until the program has started to execute but that prevents the program from continuing.

# semantic error

An error in a program that makes it do something other than what the programmer intended.

# semantics

The meaning of a program.

# shell mode

A style of using Python where we type expressions at the command prompt, and the results are shown immediately. Contrast with source code, and see the entry under Python shell.

# source code

A program, stored in a file, in a high-level language before being compiled or interpreted.

# syntax

The structure of a program.

# syntax error

An error in a program that makes it impossible to parse — and therefore impossible to interpret.

# token

One of the basic elements of the syntactic structure of a program, analogous to a word in a natural language.

# assignment statement

A statement that assigns a value to a name \(variable\). To the left of the assignment operator, `=`, is a name. To the right of the assignment token is an expression which is evaluated by the Python interpreter and then assigned to the name. The difference between the left and right hand sides of the assignment statement is often confusing to new programmers. In the following assignment:

```
n = n + 1
```

`n` plays a very different role on each side of the `=`. On the right it is a _value_ and makes up part of the _expression_ which will be evaluated by the Python interpreter before assigning it to the name on the left.

# assignment token

`=` is Python’s assignment token, which should not be confused with the mathematical comparison operator using the same symbol.

# class

see **data type** below

# comment

Information in a program that is meant for other programmers \(or anyone reading the source code\) and has no effect on the execution of the program.

# data type

A set of values. The type of a value determines how it can be used in expressions. So far, the types you have seen are integers \(`int`\), floating-point numbers \(`float`\), and strings \(`str`\).

# decrement

Decrease by 1.

# evaluate

To simplify an expression by performing the operations in order to yield a single value.

# expression

A combination of operators and operands \(variables and values\) that represents a single result value. Expressions are evaluated to give that result.

# float

A Python data type which stores _floating-point_ numbers. Floating-point numbers are stored internally in two parts: a _base_ and an _exponent_. When printed in the standard format, they look like decimal numbers. Beware of rounding errors when you use `float`s, and remember that they are only approximate values.

# increment

Both as a noun and as a verb, increment means to increase by 1.

# initialization \(of a variable\)

To initialize a variable is to give it an initial value. Since in Python variables don’t exist until they are assigned values, they are initialized when they are created. In other programming languages this is not the case, and variables can be created without being initialized, in which case they have either default or _garbage_ values.

# int

A Python data type that holds positive and negative **whole** numbers.

# integer division

An operation that divides one integer by another and yields an integer. Integer division yields only the whole number of times that the numerator is divisible by the denominator and discards any remainder.

# keyword

A reserved word that is used by the compiler to parse program; you cannot use keywords like `if`, `def`, and `while` as variable names.

# modulus operator

Also called remainder operator or integer remainder operator. Gives the remainder after performing integer division.

# object

Also known as a data object \(or data value\). The fundamental things that programs are designed to manipulate \(or that programmers ask to do things for them\).

# operand

One of the values on which an operator operates.

# operator

A special symbol that represents a simple computation like addition, multiplication, or string concatenation.

# prompt string

Used during interactive input to provide the user with hints as to what type of value to enter.

# reference diagram

A picture showing a variable with an arrow pointing to the value \(object\) that the variable refers to. See also **state snapshot**.

# rules of precedence

The set of rules governing the order in which expressions involving multiple operators and operands are evaluated.

# state snapshot

A graphical representation of a set of variables and the values to which they refer, taken at a particular instant during the program’s execution.

# statement

An instruction that the Python interpreter can execute. So far we have only seen the assignment statement, but we will soon meet the `import` statement and the `for` statement.

# str

A Python data type that holds a string of characters.

# type conversion function

A function that can convert a data value from one type to another.

# value

A number or string \(or other things to be named later\) that can be stored in a variable or computed in an expression.

# variable

A name that refers to a value.

# variable name

A name given to a variable. Variable names in Python consist of a sequence of letters \(a..z, A..Z, and \_\) and digits \(0..9\) that begins with a letter. In best programming practice, variable names should be chosen so that they describe their use in the program, making the program _self documenting_.

## Turtle



* attribute

  Some state or value that belongs to a particular object. For example, tess has a color.

* canvas

  A surface within a window where drawing takes place.

* control flow

  See *flow of execution* in the next chapter.

* deterministic

  A process that is repeatable and predictable.

* documentation

  A place where you can go to get detailed information about aspects of your programming language.

* for loop

  A statement in Python for convenient repetition of statements in the *body* of the loop.

* instance

  An object that belongs to a class. tess and alex are different instances of the class Turtle

* invoke

  An object has methods. We use the verb invoke to mean *activate the method*. Invoking a method is done by putting parentheses after the method name, with some possible arguments. So`wn.exitonclick()` is an invocation of the `exitonclick` method.

* iteration

  A basic building block for algorithms (programs). It allows steps to be repeated. Sometimes called *looping*.

* loop body

  Any number of statements nested inside a loop. The nesting is indicated by the fact that the statements are indented under the for loop statement.

* loop variable

  A variable used as part of a for loop. It is assigned a different value on each iteration of the loop, and is used as part of the terminating condition of the loop.

* method

  A function that is attached to an object. Invoking or activating the method causes the object to respond in some way, e.g. `forward` is the method when we say `tess.forward(100)`.

* module

  A file containing Python definitions and statements intended for use in other Python programs. The contents of a module are made available to the other program by using the *import* statement.

* object

  A “thing” to which a variable can refer. This could be a screen window, or one of the turtles you have created.

* pseudo-random number

  A number that is not genuinely random but is instead created algorithmically.

* random number

  A number that is generated in such a way as to exhibit statistical randomness.

* random number generator

  A function that will provide you with random numbers, usually between 0 and 1.

* range

  A built-in function in Python for generating sequences of integers. It is especially useful when we need to write a for loop that executes a fixed number of times.

* sequential

  The default behavior of a program. Step by step processing of algorithm.

* standard library

  A collection of modules that are part of the normal installation of Python.

* state

  The collection of attribute values that a specific data object maintains.

* terminating condition

  A condition that occurs which causes a loop to stop repeating its body. In the `for` loops we saw in this chapter, the terminating condition has been when there are no more elements to assign to the loop variable.

* turtle

  A data object used to create pictures (known as turtle graphics).

#### hdsafdjfd



* chatterbox function

  A function which interacts with the user (using `input` or `print`) when it should not. Silent functions that just convert their input arguments into their output results are usually the most useful ones.

* composition (of functions)

  Calling one function from within the body of another, or using the return value of one function as an argument to the call of another.

* dead code

  Part of a program that can never be executed, often because it appears after a `return` statement.

* fruitful function

  A function that yields a return value instead of `None`.

* incremental development

  A program development plan intended to simplify debugging by adding and testing only a small amount of code at a time.

* None

  A special Python value. One use in Python is that it is returned by functions that do not execute a return statement with a return argument.

* return value

  The value provided as the result of a function call.

* scaffolding

  Code that is used during program development to assist with development and debugging. The unit test code that we added in this chapter are examples of scaffolding.

* temporary variable

  A variable used to store an intermediate value in a complex calculation.

## Selection

block

A group of consecutive statements with the same indentation.

body

The block of statements in a compound statement that follows the header.

boolean expression

An expression that is either true or false.

boolean function

A function that returns a boolean value. The only possible values of the `bool` type are `False` and `True`.

boolean value

There are exactly two boolean values: `True` and `False`. Boolean values result when a boolean expression is evaluated by the Python interepreter. They have type `bool`.

branch

One of the possible paths of the flow of execution determined by conditional execution.

chained conditional

A conditional branch with more than two possible flows of execution. In Python chained conditionals are written with `if ... elif ... else` statements.

comparison operator

One of the operators that compares two values: `==`, `!=`, `>`, `<`, `>=`, and `<=`.

condition

The boolean expression in a conditional statement that determines which branch is executed.

conditional statement

A statement that controls the flow of execution depending on some condition. In Python the keywords `if`, `elif`, and `else` are used for conditional statements.

logical operator

One of the operators that combines boolean expressions: `and`, `or`, and `not`.

modulus operator

An operator, denoted with a percent sign ( `%`), that works on integers and yields the remainder when one number is divided by another.

nesting

One program structure within another, such as a conditional statement inside a branch of another conditional statement.



* collection data type

  A data type in which the values are made up of components, or elements, that are themselves values.

* default value

  The value given to an optional parameter if no argument for it is provided in the function call.

* dot notation

  Use of the **dot operator**, `.`, to access functions inside a module, or to access methods and attributes of an object.

* immutable

  A compound data type whose elements can not be assigned new values.

* index

  A variable or value used to select a member of an ordered collection, such as a character from a string, or an element from a list.

* optional parameter

  A parameter written in a function header with an assignment to a default value which it will receive if no corresponding argument is given for it in the function call.

* slice

  A part of a string (substring) specified by a range of indices. More generally, a subsequence of any sequence type in Python can be created using the slice operator (`sequence[start:stop]`).

* traverse

  To iterate through the elements of a collection, performing a similar operation on each.

* whitespace

  Any of the characters that move the cursor without printing visible characters. The constant `string.whitespace` contains all the white-space characters.

[**](https://runestone.launchcode.org/runestone/static/thinkcspy/StringsContinued/Summary.html)

[**](https://runestone.launchcode.org/runestone/static/thinkcspy/StringsContinued/Exercises.html)