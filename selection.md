## 6. Selection

### Booleans \(values and expressions\)

There are only two **boolean values**. They are `True` and `False`. They are called **boolean literals**. To work in Python must be capitalized. Type `<class 'bool'>`.

A **boolean expression** is an expression that evaluates to a boolean value.

```python
3 > 4
>>> False
5 == 5
>>> True
```

**Boolean operators**

```python
x != y               # x is not equal to y
x > y                # x is greater than y
x < y                # x is less than y
x >= y               # x is greater than or equal to y
x <= y               # x is less than or equal to y
```

The result of any expression evaluation can be returned by a function \(using the `return` statement\), functions can return boolean values aka. **boolean functions**.

It is common to give **boolean functions** names that sound like yes/no questions.

```python
def isDivisible(x, y):
    return x % y == 0
```

### Truthy values

Can be checked with `bool()`

```python
bool(1) # True
bool(0)
bool([])
bool("")
bool(" ") # True
```

### the *is* operation

```python
a = []
b = []
a is b
>>> False
```

The *is* operator is rather useless as it checks memory address, but it is very useful for comparing to None.

```python
a is None
>>> True # if of course a is None

[1] == [1]
>>> True
[1] is [1]
>>> False
```

### Logical operators

```python
# and
# or
# not
x > 0 and x < 10
n % 2 == 0 or n % 3 == 0 
not  x > y

number = 6
number == 5 or number == 6 or number == 7
# number == 5 or 6 or 7 will not work
```

### Conditional execution

#### `if` statement

```python
if BOOLEAN EXPRESSION:
    STATEMENTS_1        # executed if condition evaluates to True
else:
    STATEMENTS_2        # executed if condition evaluates to False
```

#### `unary` selection
the result of any expression evaluation can be returned by a function (using the `return` statement), functions can return boolean values

```python
if x < 0:
    print("The negative number ",  x, " is not valid here.")
```

In **unary selection** the else clause is omitted and nothing happens if the statement is `False`.

`else` block cannot be used by itself.

#### conditionals can be nested

the indentation makes it clear what belongs where, and is thus very important

```python
if x < y:
    print("x is less than y")
else:
    if x > y:
        print("x is greater than y")
    else:
        print("x and y must be equal")
```

#### chained conditionals

```python
if x < y:
    print("x is less than y")
elif x > y:
    print("x is greater than y")
else:
    print("x and y must be equal")
```

* Only a single \(and optional\) final `else` statement is allowed and it must be the last branch in the statement
* Each condition is checked in order. If the first is false, the next is checked, and so on.
* Even if **more than one condition is true**, only the first true branch executes.

#### `while` statement
The while statement provides a much more general (than `for` loop) mechanism for iterating.
The body of while will be repeated as long as the controlling boolean expression evaluates to True.

We can use the `while` loop to create any type of iteration we wish, including anything that we have previously done with a `for` loop.

```python
def sumTo(aBound):
    """ Return the sum of 1+2+3 ... n """

    theSum  = 0
    aNumber = 1
    while aNumber <= aBound:
        theSum = theSum + aNumber 
        aNumber = aNumber + 1
    return theSum
```

The body of the loop should change the value of one or more variables so that eventually the condition becomes `False` and the loop terminates. Otherwise the loop will repeat forever. This is called an **infinite loop**.

* `for` loops create **definite iteration** because they loop through define number of items in a range
* `while` statement creates an **indefinite iteration** because we do not know how many times it may iterate.

#### escape character

The string `'\t'` represents a **tab character**. The backslash character in `'\t'` indicates the beginning of an **escape sequence**. Escape sequences are used to represent invisible characters like tabs and newlines. The sequence `'\n'` represents a **newline**.



### 2-dimensional iteration - image manipulation

#### RGB Color Model

The amount of each color, sometimes called the **intensity** of the color, allows us to have very fine control over the resulting color.

The minimum intensity value for a basic color is 0. For example if the red intensity is 0, then there is no red in the pixel. The maximum intensity is 255. 

| Color       | Red  | Green | Blue |
| ----------- | ---- | ----- | ---- |
| **Red**     | 255  | 0     | 0    |
| **Green**   | 0    | 255   | 0    |
| **Blue**    | 0    | 0     | 255  |
| **White**   | 255  | 255   | 255  |
| **Black**   | 0    | 0     | 0    |
| **Yellow**  | 255  | 255   | 0    |
| **Magenta** | 255  | 0     | 255  |

```python
import image
```

**`image`** module has two classes: `Image` and `Pixel`. 

There are methods to work with images pixel-per-pixel.

| Method Name  | Example          | Explanation                              |
| ------------ | ---------------- | ---------------------------------------- |
| Pixel(r,g,b) | Pixel(20,100,50) | Create a new pixel with 20 red, 100 green, and 50 blue. |
| getRed()     | r = p.getRed()   | Return the red component intensity.      |
| getGreen()   | r = p.getGreen() | Return the green component intensity.    |
| getBlue()    | r = p.getBlue()  | Return the blue component intensity.     |
| setRed()     | p.setRed(100)    | Set the red component intensity to 100.  |
| setGreen()   | p.setGreen(45)   | Set the green component intensity to 45. |
| setBlue()    | p.setBlue(156)   | Set the blue component intensity to 156. |

Methods to worth with image class:

| Method Name         | Example                         | Explanation                              |
| ------------------- | ------------------------------- | ---------------------------------------- |
| Image(filename)     | img = image.Image(“cy.png”)     | Create an Image object from the file cy.png. |
| EmptyImage()        | img = image.EmptyImage(100,200) | Create an Image object that has all “White” pixels |
| getWidth()          | w = img.getWidth()              | Return the width of the image in pixels. |
| getHeight()         | h = img.getHeight()             | Return the height of the image in pixels. |
| getPixel(col,row)   | p = img.getPixel(35,86)         | Return the pixel at column 35, row 86.   |
| setPixel(col,row,p) | img.setPixel(100,50,mp)         | Set the pixel at column 100, row 50 to be mp. |

### nested iteration

**Image processing** refers to the ability to manipulate the individual pixels in a digital image. In order to process all of the pixels, we need to be able to systematically visit all of the rows and columns in the image. The best way to do this is to use **nested iteration**.

```python
for i in range(5):
    for j in range(3):
        print(i, j)
```

```python
for row in range(img.getHeight()):
    for col in range(img.getWidth()):
        # do something with the pixel at position (col,row)
```

