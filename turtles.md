## 4. Turtles

```python
import turtle               # allows us to use the turtles library/module
window = turtle.Screen()        # creates a graphics window
alex = turtle.Turtle()      # create a turtle named alex
alex.forward(150)           # tell the object alex to move forward by 150 units invoking .forward method
alex.left(90)               # turn by 90 degrees
alex.forward(75)            # complete the second side of a rectangle
```

assign to alex *“The **Turtle** type that is defined within the **turtle** module”*

```
alex = turtle.Turtle()
```

* turtle starts off facing east when it is created (it is just part of the turtle library)
* **Objects** can have **methods** (things that they can do), and **properties** (things they are):
  * move_forward - m
  * jump - m
  * color - p
  * age - p

```python
import turtle
window = turtle.Screen()
window.bgcolor("lightgreen")	# property

tess = turtle.Turtle()
tess.color("blue")              # property
tess.pensize(3)					# property

tess.forward(50)				# method
tess.left(120)					# method
tess.forward(50)				# method

window.exitonclick()			# method
```



### Instances

Each instance has own properties, and methods. 

```python
import turtle
wn = turtle.Screen()             # Set up the window and its attributes
wn.bgcolor("lightgreen")


tess = turtle.Turtle()           # create tess and set some attributes
tess.color("hotpink")
tess.pensize(5)

alex = turtle.Turtle()           # create alex

tess.forward(80)                 # Let tess draw an equilateral triangle
tess.left(120)
tess.forward(80)
tess.left(120)
tess.forward(80)
tess.left(120)                   # complete the triangle

tess.right(180)                  # turn tess around
tess.forward(80)                 # move her away from the origin

alex.forward(50)                 # make alex draw a square
alex.left(90)
alex.forward(50)
alex.left(90)
alex.forward(50)
alex.left(90)
alex.forward(50)
alex.left(90)

wn.exitonclick()
```

### For Loop

A basic building block of all programs is to be able to repeat some code over and over again. In computer science, we refer to this repetitive idea as **iteration**.

In Python, the **for** statement allows us to write programs that implement iteration. 

```python
for name in ["Joe", "Amy", "Brad", "Angelina", "Zuki", "Thandi", "Paris"]:
    print("Hi", name, "Please come to my party on Saturday!")
```

* **name** in this `for` statement is called the **loop variable**, it is being updated after each run
* **list** of names
* line 2 is the **loop body** !!! ALWAYS INDENTED
* **terminating condition** - if the conditions to iterate again are over, it is called t.c
* **control flow** aka. **flow of execution** of the program/loop is the name for python to know where in the loop we are at any given moment
  * **sequential** control flow == **linear**


![control_flow](images/control_flow.png)

### Iteration simplifies programs

```python
import turtle            # set up alex
wn = turtle.Screen()
alex = turtle.Turtle()

for i in [0, 1, 2, 3]:      # repeat four times
    alex.forward(50)
    alex.left(90)

wn.exitonclick()

```

Benefits:

* simplified program - easier to understand
* found patterns of behaviour that can be reused

The range values, had nothing to do whith the loop number, anything could be inside:

```python
for aColor in ["yellow", "red", "purple", "blue"]:      # repeat four times
    alex.forward(50)
    alex.left(90)
```

would work the same, plus the change of the color.

 ### `range` function

```python
for i in range(4):
    # Executes the body with i = 0, then 1, then 2, then 3
for x in range(10):
    # sets x to each of ... [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
```

```python
a = range(1,5)			#range(start, stop)
print(a)
>>> [1,2,3,4]

b = range(2,9,2)		#range(start,stop,step)
print(b)
>>> [2,4,6,8]

c = print(range(10, 0, -1))
print(c)
>>> [10, 9, 8, 7, 6, 5, 4, 3, 2, 1]
```

### Turtle specific methods

```python
turtle.backward(-100) # will go forward
turtle.left(-30) #will turn right
turtle.up() /penup()
turtle.down() /pendown() # refers to up and down for pen drawing 
turtle.shape("turtle")
turtle.speed(10)
turtle.stamp() # stamp its inprint to canvas, not pen
```

Every turtle can have its own shape. The ones available “out of the box” are `arrow`, `blank`, `circle`, `classic`, `square`, `triangle`, `turtle`.

| Method     | Parameters | Description                              |
| ---------- | ---------- | ---------------------------------------- |
| Turtle     | None       | Creates and returns a new turtle object  |
| forward    | distance   | Moves the turtle forward                 |
| backward   | distance   | Moves the turle backward                 |
| right      | angle      | Turns the turtle clockwise               |
| left       | angle      | Turns the turtle counter clockwise       |
| up         | None       | Picks up the turtles tail                |
| down       | None       | Puts down the turtles tail               |
| color      | color name | Changes the color of the turtle’s tail   |
| fillcolor  | color name | Changes the color of the turtle will use to fill a polygon |
| heading    | None       | Returns the current heading              |
| position   | None       | Returns the current position             |
| goto       | x,y        | Move the turtle to position x,y          |
| begin_fill | None       | Remember the starting point for a filled polygon |
| end_fill   | None       | Close the polygon and fill with the current fill color |
| dot        | None       | Leave a dot at the current position      |
| stamp      | None       | Leaves an impression of a turtle shape at the current location |
| shape      | shapename  | Should be ‘arrow’, ‘classic’, ‘turtle’, or ‘circle’ |

[Turtle Docs](http://docs.python.org/dev/py3k/library/turtle.html)

### Modules

A **module** is a file containing Python definitions and statements intended for use in other Python programs. There are many Python modules that come with Python as part of the **standard library**. 

* [Global module index](http://docs.python.org/py3k/py-modindex.html) to find things
* [Language reference](http://docs.python.org/py3k/reference/index.html)
* [Tutorial](http://docs.python.org/py3k/tutorial/index.html)

### The `math` and `random` modules

* [Math module docs](http://docs.python.org/py3k/library/math.html#module-math)

The `math` module contains the kinds of mathematical functions you would typically find on your calculator and some mathematical constants like pi and e. As we noted above, when we `import math`, we create a reference to a module object that contains these elements.

```python
import math

print(math.pi)
print(math.e)

print(math.sqrt(2.0))

print(math.sin(math.radians(90)))   # sin of 90 degrees
```

The random module:

* `random.random()`
* `random.randrange()`

```python
import random

prob = random.random()
print(prob)

diceThrow = random.randrange(1, 7)       # return an int, one of 1,2,3,4,5,6
print(diceThrow)

>>> 0.885404889175
>>> 2
```

* **pseudo-random** since they depend on seed value