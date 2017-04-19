## 6. Selection

### Booleans (values and expressions)

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

The result of any expression evaluation can be returned by a function (using the `return` statement), functions can return boolean values aka. **boolean functions**.

It is common to give **boolean functions** names that sound like yes/no questions. 

```python
def isDivisible(x, y):
    return x % y == 0
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

###  Conditional execution

#### `if` statement

```python
if BOOLEAN EXPRESSION:
    STATEMENTS_1        # executed if condition evaluates to True
else:
    STATEMENTS_2        # executed if condition evaluates to False
```

#### `unary` selection

```python
if x < 0:the result of any expression evaluation can be returned by a function (using the return statement), functions can return boolean values
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

* Only a single (and optional) final `else` statement is allowed and it must be the last branch in the statement
* Each condition is checked in order. If the first is false, the next is checked, and so on.
* Even if **more than one condition is true**, only the first true branch executes.