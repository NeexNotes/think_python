## 3. Debugging
### What is Debugging?

**Debugging** is the process of tracking down and correcting erros in code. The erors are called **bugs**.

Three kinds of errors can occur in a program: 

* [syntax errors](http://en.wikipedia.org/wiki/Syntax_error)
* [runtime errors](http://en.wikipedia.org/wiki/Runtime_error)
* [semantic errors](http://en.wikipedia.org/wiki/Logic_error)

### Syntax errors

**Syntax** refers to the structure of a program and the rules about that structure. AKA **GRAMMAR**.

Python <u>does not run</u> if there is a single error. Unlike JavaScript, HTML and CSS rendering in the browsers.

Found by **compiler/interpreter** on the fly.

### Runtime errors

The error does not appear until the program run. These errors are also called **exceptions** because they usually indicate that something exceptional (and bad) has happened.

E.g dividing by zero is a runtime error. Python will not see it with 100% because it could be an input from user. It is forbidden as of rules, but it will appear during runtime. 

### Semantic errors

The problem is that the program you wrote is not the program you wanted to write. It is an error that makes your program do the wrong thing, even if the code syntax is 100% fine.

### Experimental Debugging

For some people, programming and debugging are the same thing. That is, programming is the process of gradually debugging a program until it does what you want. 

Start with **something**, and than make it better. Small steps approach.

### How to be a Successful Programmer

* start small
* break things down
* debug
* get happy
* move to the next small thing

###  Avoiding debugging

* start small (again)
* keep it working

> **Get something working and keep it working**

* test things as you go
* think of boundary conditions

Debugging tips:

* read error messages, no really do!
* use print statements

> Our brain tends to see what we think is there.

### Errors in Python

1. **ParseError** - error in the syntax
2. **TypeError** - try to combine two objects that are not compatible
3. **NameError** - typo of any kind, in variable, in function, etc
4. **ValueError** -  wrong value to work with, for example: `int("")`
5. **URIError**
6. **TokenError**
7. **SyntaxError**
8. **TimeLimitError**
9. **IndentationError**
10. **AttributeError**
11. **ImportError**
12. **IndexError**


