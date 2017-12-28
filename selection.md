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

### the *in* operation

```python
"py" in "python"
>>> True

5 in [3,4,5]
>>> True
```

The not keyword ca be used both ways:

```python
if "a" not in "hello":
    pass

if not "a" in "hello":
    pass
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

### break me out of jail (or not) keywords

#### break

You can stop a loop early by using the keyword `break`.

```python
for letter in "abcdef":
    if letter == "c":
        break
    print(letter)
```

This loop will print `"a"` and `"b"` and then stop because of the `break` when `letter` is `"c"`. `break` can only be used inside of a loop.

#### continue

```python
for letter in "abcdef":
    if letter == "c":
        continue
    print(letter)
```

Nearly the same loop but this one will print `"a"`, `"b"`, `"d"`, `"e"`, and `"f"`. It skips `"c"` because of the `continue`, which causes the loop to immediately move on to the next step in the loop.

Like `break`, `continue` can only be used inside of a loop.

