## 5. Functions

* it is a named sequence of statements that belong together
* primary purpose is to help organize the code into chunks similar to how we think of the solutions

```python
def name( parameters ):
    statements
```

* name must follow the naming rules as before
* parameters are data needed for the function to do what it needs to do
* **formal parameters** - parameters in function definition
* **actual parameters** or **arguments** - values passed in function call
* using the function is called **function call** or **function invocation**
* **fruitful functions** - functions that return a value. In many other languages, a chunk that doesn't return a value is called a **procedure**.
* separate function definitions with **two blank lines**

#### `docstring` 

First string (triple-quote by most tools) in function, is a docstring, that is treated specially. It can be accessed by `function_name.__doc__` . It is used by most programmers to store key info for the function.

#### `return`

```python
def square(x):
    y = x * x
    return y

toSquare = 10
result = square(toSquare)
print("The result of ", toSquare, " squared is ", result)
```

The **return** statement is followed by an expression which is evaluated. Its result is returned to the caller as the **“fruit”** of calling this function.

Finally, there is one more aspect of function **return** values that should be noted. All Python functions return the value `None` unless there is an explicit return statement with a value other than `None`.

### Local vs. Global

First, Python looks at the variables that are defined as local variables in the function. We call this the **local scope**. If the variable name is not found in the local scope, then Python looks at the global variables, or **global scope**.

When a local variable has the same name as a global variable we say that the local shadows the global. A **shadow** means that the global variable cannot be accessed by Python because the local variable will be found first.

### Calling functions

* process of breaking a problem into smaller subproblems is called **functional decomposition**.
* functions can call other functions
* creating functions can hide the steps that are obscure, difficult or long, and create an **abstraction** by just doing the job, where we do not care how

### Using `main` function

In many programming languages (e.g. Java and C++), it is not possible to simply have statements sitting alone at the bottom of the program. They are required to be part of a special function that is automatically invoked by the operating system when the program is executed. 

This special function is called **main**. Although this is not required by the Python programming language, it is actually a good idea that we can incorporate into the logical structure of our program. 

```python
import turtle

def drawSquare(t, sz):
    """Make turtle t draw a square of with side sz."""

    for i in range(4):
        t.forward(sz)
        t.left(90)


def main():                      # Define the main function
    wn = turtle.Screen()         # Set up the window and its attributes
    wn.bgcolor("lightgreen")

    alex = turtle.Turtle()       # create alex
    drawSquare(alex, 50)         # Call the function to draw the square

    wn.exitonclick()

main()                           # Invoke the main function
```

#### `__name__ = "__main__"`

Before the Python interpreter executes your program, it defines a few special variables. One of those variables is called `__name__` and it is automatically set to the string value `"__main__"` when the program is being executed by itself in a standalone fashion. 

On the other hand, if the program is being imported by another program, then the `__name__` variable is set to the name of that module.

```python
def squareit(n):
    return n * n

def cubeit(n):
    return n*n*n

def main():
    anum = int(input("Please enter a number"))
    print(squareit(anum))
    print(cubeit(anum))

if __name__ == "__main__":
    main()
```

Line 12 uses an `if` statement to ask about the value of the `__name__` variable. If the value is `"__main__"`, then the `main` function will be called. Otherwise, it can be assumed that the program is being imported into another program and we do not want to call `main` because that program will invoke the functions as needed.

### Turtle bar chart

```python
import turtle

def drawBar(t, height):
    """ Get turtle t to draw one bar, of height. """
    t.begin_fill()               # start filling this shape
    t.left(90)
    t.forward(height)
    t.write(str(height))
    t.right(90)
    t.forward(40)
    t.right(90)
    t.forward(height)
    t.left(90)
    t.end_fill()                 # stop filling this shape



xs = [48, 117, 200, 240, 160, 260, 220]  # here is the data
maxheight = max(xs)
numbars = len(xs)
border = 10

wn = turtle.Screen()             # Set up the window and its attributes
wn.setworldcoordinates(0-border, 0-border, 40*numbars+border, maxheight+border)
wn.bgcolor("lightgreen")

tess = turtle.Turtle()           # create tess and set some attributes
tess.color("blue")
tess.fillcolor("red")
tess.pensize(3)



for a in xs:
    drawBar(tess, a)

wn.exitonclick()
```



* separate function definitions with two blank lines


* ​
* ​
* ​
* ​
* [8. Program Development](https://runestone.launchcode.org/runestone/static/thinkcspy/Functions/ProgramDevelopment.html)
* [9. Composition](https://runestone.launchcode.org/runestone/static/thinkcspy/Functions/Composition.html)
* [10. A Turtle Bar Chart](https://runestone.launchcode.org/runestone/static/thinkcspy/Functions/ATurtleBarChart.html)
* [11. Programming With Style](https://runestone.launchcode.org/runestone/static/thinkcspy/Functions/ProgrammingWithStyle.html)
* [12. Glossary](https://runestone.launchcode.org/runestone/static/thinkcspy/Functions/Glossary.html)
* [13. Exercises](https://runestone.launchcode.org/runestone/static/thinkcspy/Functions/Exercises.html)

## 

## 

## 



