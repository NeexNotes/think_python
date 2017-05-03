## 13. Classes and Objects

Object-oriented programming \(OOP\) is a programming paradigm based on the concept of **"objects"**, which may contain data, in the form of fields, often known as **attributes**; and code, in the form of procedures, often known as **methods**.

A feature of objects is that an object's procedures can access and often modify the data fields of the object with which they are associated \(objects have a notion of "this" or "self"\).

In OOP, computer programs are designed by making them out of objects that interact with one another. There is significant diversity of OOP languages, but the most popular ones are class-based, meaning that objects are instances of classes, which typically also determine their type.

Other [programming paradigms](https://en.wikipedia.org/wiki/Programming_paradigm).

### A change of perspective

**Functions vs Objects:**

```python
tess.forward(100)
# vs.
forward(tess, 100)
```

* Hey tess object, can you move forward 100 steps.
* Hey forward function, can you move tess 100 steps.

It may not initially be obvious that it is useful. But it turns out that often times shifting responsibility from the functions onto the objects makes it possible to write more versatile functions and makes it easier to maintain and reuse code.

The most important advantage of the object-oriented style is that it fits our **mental chunking** and real-life experience more accurately. In real life our **cook** method is part of our **microwave oven** — we **don’t have a cook function sitting in the corner** of the kitchen, into which **we pass the microwave!**

> In Python, every value is actually an object. Whether it be a turtle, a list, or even an integer, they are all objects.
>
> Programs manipulate those objects, either by performing computation with them or by asking them to perform methods.

### Object inside:

**object**

* has an **internal state**
* a collection of **methods** that it can perform

**State** - represents things that the object knows about itself.

```
turtle object state:
* turtle’s position
* its color
* its heading, ....
```

**Methods** - are functions that allow you to change its state or ask questions about its state.

Methods are like the actions that an object is able to do, or the questions that an object is able to answer about itself.

```
turtle object methods:
* ability to go forward
* backward
* turn right 
* or left
cause change of internal state

* position
causes no change, returns a value to report back to you
```

### User defined classes - making a point

It can helpful to have data objects that are uniquely tailored to represent concepts related to the specific problem we are trying to solve.

A custom class pretty much always comes about when you want to cluster together a few disparate pieces of information into one larger coherent concept.

#### example: mathematical point

In two dimensions, a point is two numbers \(coordinates\) that are treated collectively as a single object.

Points are often written in parentheses with a comma separating the coordinates.

For example:

* \(0, 0\) represents the origin
* and \(x, y\) represents the point x units to the right and y units up from the origin

This \(x,y\) is the state of the point.

Some of the typical operations that one associates with points might be to:

* ask the point for its x coordinate
* ask for its y coordinate

For these operations, we can create methods with names like `getX` and `getY`.

There are also more interesting questions we might want to ask about a point.

* calculate the distance of a point from the origin
* distance of a point from another point
* find the midpoint between two points
* answer the question as to whether a point falls within a given rectangle or circle

### Syntax for Defining and Using a Class \(CamelCase naming\)

```python
class Point:
    """ Point class for representing and manipulating x,y coordinates. """

    def __init__(self):
        """ Create a new point at the origin """
        self.x = 0
        self.y = 0

# now let's create some Points!
p = Point() # p is a point
q = Point() # q is a different point

print("Nothing seems to have happened with the points")
```

Our Point class has only one method so far, `__init__`. Any time you create a new class, you should include a method with the special name `__init__`.

This **initializer** method is automatically called whenever a new instance of Point is created.

It gives the programmer \(you\) the opportunity to set up the attributes required within the new instance by giving them their initial state values.

The **self parameter** \(you could choose any other name, but nobody ever does!\) is automatically set to reference the newly-created object that needs to be initialized.

> TODO: confusing what is and is not returned.

You can see that when we invoke the `Point()`, Python creates a new “empty” Point object, and then passes that point into our `__init__` method. Inside the `__init__` method we are able to give that point two attributes called `x` and `y`, and set `x` and `y` equal to 0. Finally, the new point is returned and we assign it to the `p` variable.

### Classes vs Objects \(or Instances\)

```python
p = Point()
q = Point()

print(p)
print(q)

print(p is q)

>>> <__main__.Point object>
>>> <__main__.Point object>
>>> False
```

### Constructors

A function invocation like Turtle\(\) or Point\(\), which creates a new object instance, is called a **constructor**.

Every class automatically uses the name of the class as the name of the constructor function.

When the constructor function is invoked, a new instance of Point or Turtle is created, and then inside the `__init__` function you have the opportunity to configure the new instance into some kind of reasonable “default starting state”.

> It may be helpful to think of a class as a **factory** for making objects.
>
> The class itself isn’t an instance of a point, but it contains the machinery to make point instances. Every time you call the constructor, you’re asking the factory to make you a new object. As the object comes off the production line, its initialization method is executed in order to get the object properly set up with its factory default settings.

The combined process of “make me a new object” and “get its settings initialized to the factory default settings” is called **instantiation**.

### Adding functionality to constructor

We can make our class constructor more general by putting extra parameters into the`__init__`method.

```python
class Point:
    """ Point class for representing and manipulating x,y coordinates. """

    def __init__(self, initX, initY):
        """ Create a new point at the given coordinates. """
        self.x = initX
        self.y = initY
	
	p = Point(7, 6)
```

Now when we create new points, we supply the x and y coordinates as parameters.

#### Add methods
Let’s add two simple methods to allow a point to give us information about its state.

##### importance of self

One thing to notice is that even though the `getX` method does not need any other parameter information to do its work, there is still one formal parameter, `self`. As we stated earlier, all methods defined in a class that operate on objects of that class will have `self` as their first parameter. Again, this serves as reference to the object itself which in turn gives access to the state data inside the object.

```python
class Point:
    """ Point class for representing and manipulating x,y coordinates. """

    def __init__(self, initX, initY):
        """ Create a new point at the given coordinates. """
        self.x = initX
        self.y = initY

    def getX(self):
        return self.x

    def getY(self):
        return self.y


p = Point(7, 6)
print(p.getX())
print(p.getY())
```

Let's add `distanceFromOrigin` that will calculate the distance. It uses diagonal formula for polygon (przekątną prostokąta).

```python
class Point:
    """ Point class for representing and manipulating x,y coordinates. """

    def __init__(self, initX, initY):
        """ Create a new point at the given coordinates. """
        self.x = initX
        self.y = initY

    def getX(self):
        return self.x

    def getY(self):
        return self.y

    def distanceFromOrigin(self):
        return ((self.x ** 2) + (self.y ** 2)) ** 0.5


p = Point(7, 6)
print(p.distanceFromOrigin())

>>> 9.21954445729
```
### passing objects into functions

Here is a simple function called `distance` involving our new Point objects. The job of this function is to figure out the distance between two points.

```python
import math

class Point:
    """ Point class for representing and manipulating x,y coordinates. """

    def __init__(self, initX, initY):
        """ Create a new point at the given coordinates. """
        self.x = initX
        self.y = initY

    def getX(self):
        return self.x

    def getY(self):
        return self.y

    def distanceFromOrigin(self):
        return ((self.x ** 2) + (self.y ** 2)) ** 0.5

def distance(point1, point2):
    xdiff = point2.getX() - point1.getX()
    ydiff = point2.getY() - point1.getY()

    dist = math.sqrt(xdiff**2 + ydiff**2)
    return dist

p = Point(4, 3)
q = Point(0, 0)
print(distance(p, q))

>>> 5.0
```

### Converting an Object to a String

When we’re working with classes and objects, it is often necessary to print an object (that is to print the state of an object).

This does not work.

```python
p = Point(7, 6)
print(p)

>>> <__main__.Point object>
```
This does not work.




  


