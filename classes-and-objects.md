## 13. Classes and Objects (mutable)

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
This does not work the way we would most likely want it. The print function shown above produces a **string representation** of the Point `p`. The default functionality provided by Python tells you that p is an object of type Point. However, it does not tell you anything about the specific state of the point.

We can improve on this representation if we include a special method call `__str__`. Notice that this method uses the same naming convention as the constructor, that is two underscores before and after the name. It is common that Python uses this naming technique for special methods.

In other words, you as the programmer, get to choose what a Point should look like when it gets printed. In this case, we have decided that the string representation will include the values of x and y as well as some identifying text. It is required that the `__str__` method create and return a string.

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

    def __str__(self):
        return "x=" + str(self.x) + ", y=" + str(self.y)

p = Point(7, 6)
print(p)

>>> x=7, y=6
```

### Overriding Python functionality 
Now, you ask, don’t we already have an `str` type converter that can turn our object into a string? Yes we do!

And doesn’t print automatically use this when printing things? Yes again!

But, as we saw earlier, these automatic mechanisms do not do exactly what we want. Python provides many default implementations for methods that we as programmers will probably want to change. When a programmer changes the meaning of a special method we say that we override the method. Note also that the `str` type converter function uses whatever `__str__` method we provide.

### Instances as Return Values

```python
class Point:

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

    def __str__(self):
        return "x=" + str(self.x) + ", y=" + str(self.y)

    def halfway(self, target):
         mx = (self.x + target.x) / 2
         my = (self.y + target.y) / 2
         return Point(mx, my)

p = Point(3, 4)
q = Point(5, 12)
mid = p.halfway(q)

print(mid)
print(mid.getX())
print(mid.getY())

>>> x=4.0, y=8.0
>>> 4.0
>>> 8.0
```

### Fractions

A fraction is most commonly thought of as two integers, one over the other, with a line separating them. 

The number on the **top** is called the **numerator** and the number on the **bottom** is called the **denominator** => numerator/denominator

To design our class, we simply need to use the analysis above to realize that the state of a fraction object can be completely described by representing two integers.

```python
class Fraction:

    def __init__(self, top, bottom):

        self.num = top        # the numerator is on top
        self.den = bottom     # the denominator is on the bottom

    def __str__(self):
        return str(self.num) + "/" + str(self.den)

    def getNum(self):
        return self.num

    def getDen(self):
        return self.den

myfraction = Fraction(3, 4)
print(myfraction)

print(myfraction.getNum())
print(myfraction.getDen())
```

### implementing outside function

```python
def gcd(m, n):
    while m % n != 0:
        oldm = m
        oldn = n

        m = oldn
        n = oldm % oldn

    return n

class Fraction:

    def __init__(self, top, bottom):

        self.num = top        # the numerator is on top
        self.den = bottom     # the denominator is on the bottom

    def __str__(self):
        return str(self.num) + "/" + str(self.den)

    def simplify(self):
        common = gcd(self.num, self.den)

        self.num = self.num // common
        self.den = self.den // common

myfraction = Fraction(12, 16)

print(myfraction)
myfraction.simplify()
print(myfraction)
```

The greatest common divisor can be useful to other classes so it is outside. It is a helper function.

Second, the `simplify` method does not return anything. Its job is to modify the object itself. This type of method is known as a **mutator** method because it mutates or changes the internal state of the object.

### Sameness

If you say, Chris and I have the same car, you mean that his car and yours are the same make and model, but that they are two different cars. If you say, Chris and I have the same mother, you mean that his mother and yours are the same person.

```python
class Fraction:

    def __init__(self, top, bottom):

        self.num = top        # the numerator is on top
        self.den = bottom     # the denominator is on the bottom

    def __str__(self):
        return str(self.num) + "/" + str(self.den)


myfraction = Fraction(3, 4)
yourfraction = Fraction(3, 4)
print(myfraction is yourfraction)

ourfraction = myfraction
print(myfraction is ourfraction)

>>> False
>>> True
```

This type of equality is called **shallow equality** because it compares only the references, not the contents of the objects.

We could define equality to mean the fractions are the same in that they have the same numerator and the same denominator.

```python
def sameFraction(f1, f2):
    return (f1.getNum() == f2.getNum()) and (f1.getDen() == f2.getDen())
```

This type of equality is known as **deep equality** since it compares the values *deep* in the object, not just the reference to the object.

### !!! ALERT `==` isn't always testing the same way 

```python
p = Point(4, 2)
s = Point(4, 2)
print("== on Points returns", p == s)  # by default, == does a shallow equality test here

a = [2, 3]
b = [2, 3]
print("== on lists returns",  a == b)  # by default, == does a deep equality test on lists

>>> == on Points returns False
>>> == on lists returns True
```

## Arithmetic methods

```python
def add(self,otherfraction):

    newnum = self.num*otherfraction.den + self.den*otherfraction.num
    newden = self.den * otherfraction.den

    common = gcd(newnum,newden)

    return Fraction(newnum//common,newden//common)
```

One final modification to this method will be quite useful. Instead invoking the `add` method, we can use the addition operator “+”. This requires that we implement another special method, this time called `__add__`. The details of the method are the same.

```python
def __add__(self, otherfraction):

    newnum = self.num*otherfraction.den + self.den*otherfraction.num
    newden = self.den * otherfraction.den

    common = gcd(newnum, newden)

    return Fraction(newnum // common, newden // common)	

f1 = Fraction(1, 2)
f2 = Fraction(1, 4)

f3 = f1 + f2    # calls the __add__ method of f1
print(f3)

>>> 3/4
```

### Inheritance

```python
class Cat:

    def __init__(self):
        # every Cat comes into this world tired and hungry
        self.tired = True
        self.hungry = True

    def sleep(self):
        self.tired = False
        # a Cat always wakes up hungry
        self.hungry = True

    def eat(self):
        if self.hungry:
            self.hungry = False
        else:
            # eating when already full makes a Cat sleepy
            self.tired = True

    def noise(self):
        # sleepy cats say prrrr, energized cats say meow!
        if self.tired:
            return "prrrr"
        else:
            return "meow!"

tom = Cat()
print("tom says:", tom.noise())
tom.sleep()
print("After sleeping, tom says:", tom.noise())
tom.eat()
print("After eating, tom still says:", tom.noise())
tom.eat()
print("After eating again, tom says:", tom.noise())
```

Now let’s say we want to create another class to represent a tiger. Tigers will be pretty similar to cats, except for the following additions:

* tigers can be *angry*. Specifically, a tiger is angry whenever it is both hungry and tired.
* If a tiger is angry, its noise is `"GRRRR!"`.

How should we go about implementing this `Tiger` class?  The naive solution would be to copy and paste our `Cat` class, and then modify things as necessary:

```python
class Tiger:

    def __init__(self):
        # every Tiger comes into this world tired and hungry
        self.tired = True
        self.hungry = True

    def sleep(self):
        self.tired = False
        # a Tiger always wakes up hungry
        self.hungry = True

    def eat(self):
        if self.hungry:
            self.hungry = False
        else:
            # eating when already full makes a Tiger sleepy
            self.tired = True

    def angry(self):
        # a Tiger is angry whenever it is both hungry and tired
        return self.tired and self.hungry

    def noise(self):
        if self.angry():
            # angry Tigers say GRRRR!
            return "GRRRR!"
        elif self.tired:
            return "prrrr"
        else:
            return "meow!"


hobbes = Tiger()
print("hobbes says:", hobbes.noise())
hobbes.sleep()
print("After sleeping, hobbes says:", hobbes.noise())
hobbes.eat()
print("After eating, hobbes still says:", hobbes.noise())
hobbes.eat()
print("After eating again, hobbes says:", hobbes.noise())
```

Ideally there should be some way of defining a `Tiger` class without having to repeat all the aspects that we already defined in the `Cat` class. We want to be able to say “A Tiger is exactly like a Cat, except for a few additions and modifications, which are: [blah blah blah]”.

This is exactly what inheritance allows us to do. Inheritance is a syntax for defining a custom class that *inherits* much of its structure and behavior from some other class. In our example, the `Tiger` class inherits much of its structure and behavior from the `Cat` class. Here’s how we can implement that relationship in Python:

```python
class Cat:

    def __init__(self):
        # every Cat comes into this world tired and hungry
        self.tired = True
        self.hungry = True

    def sleep(self):
        self.tired = False
        # a Cat always wakes up hungry
        self.hungry = True

    def eat(self):
        if self.hungry:
            self.hungry = False
        else:
            # eating when already full makes a Cat sleepy
            self.tired = True

    def noise(self):
        # sleepy cats say prrrr, energized cats say meow!
        if self.tired:
            return "prrrr"
        else:
            return "meow!"


class Tiger(Cat): # notice the (Cat) in parentheses

    def angry(self):
        # a Tiger is angry whenever it is both hungry and tired
        return self.tired and self.hungry

    def noise(self):
        if self.angry():
            # an angry Tiger says GRRRR!
            return "GRRRR!"
        else:
            # a non-angry Tiger behaves like a Cat
            return Cat.noise(self)


hobbes = Tiger()
print("hobbes says:", hobbes.noise())
hobbes.sleep()
print("After sleeping, hobbes says:", hobbes.noise())
hobbes.eat()
print("After eating, hobbes still says:", hobbes.noise())
hobbes.eat()
print("After eating again, hobbes says:", hobbes.noise())
```

* We define the inheritance relationship by writing `class Tiger(Cat)`. In general, the syntax for any subclass that inherits from some “superclass” is:

  ```python
  class MySubclass(MySuperclass):
      # method definitions for MySubclass
  ```

* Our `Tiger` definition is very short. This is because we *only* needed to define the things that distinguish a `Tiger` from a `Cat`. Specifically, we added a new method, `angry`, and we modified an existing method, `noise`. That’s all. The important point is that we were able to create a `Tiger`named `hobbes` and command him to eat and sleep, *without* having to write any code in our `Tiger`class to define the `eat`, `sleep` or `__init__` methods, or the `tired` and `hungry` attributes. We get to use all those methods and attributes “for free” just by virtue of inheriting from the `Cat` class.

* The `Tiger` class *overrides* the `noise` method. When we invoke `hobbes.noise()`, we are invoking the `Tiger.noise` function. This gives our tiger the opportunity to return something different than a cat would. But notice that if the tiger is not angry, then our `else` branch contains this line:

  ```
  else:
      return Cat.noise(self)
  ```

  That code essentially says: “I’m not angry, so I will just return whatever a Cat would normally return here.” In other words, the tiger *defers responsibility* to its cat superclass. You might say the tiger allows its more basic cat instincts to take over.

To recap: inheritance allows you to define new types like `Tiger` by “extending” the code from previously defined types like `Cat`. A subclass like `Tiger` inherits all the functionality of its superclass, but can additionally define its own new attributes and methods (such as the `angry` method), and can override the implementation of preexisting methods (such as the `noise` method).

## Another Cat Subclass