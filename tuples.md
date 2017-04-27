## Tuples

### Mutability

Sequential collections (so far):

* **string** - immutable
* **list** - mutable
* **tuple** - immutable

> A **tuple**, like a list, is a sequence of items of any type. Unlike lists, however, tuples are immutable.

Syntactically, a tuple is a comma-separated sequence of values. Although it is not necessary, it is conventional to enclose tuples in parentheses:

```python
julia = ("Julia", "Roberts", 1967, "Duplicity", 2009, "Actress", "Atlanta, Georgia")
```

Tuples are useful for representing what other languages often call **records** — some related information that belongs together, like your student record. There is no description of what each of these **fields** means, but we can guess.

All info about Julia can be represented with one variable by using a tuple.

Tuples support the same sequence operations as strings and lists. For example, the index operator selects an element from a tuple.

```python
julia = ("Julia", "Roberts", 1967, "Duplicity", 2009, "Actress", "Atlanta, Georgia")
print(julia[2])
print(julia[2:6])

print(len(julia))

julia = julia[:3] + ("Eat Pray Love", 2010) + julia[5:]
print(julia)

>>> 1967
>>> (1967, 'Duplicity', 2009, 'Actress')
>>> 7
>>> ('Julia', 'Roberts', 1967, 'Eat Pray Love', 2010, 'Actress', 'Atlanta, Georgia')
```

### Single element tuple

To create a tuple with a single element (but you’re probably not likely to do that too often), we have to include the final comma, because without the final comma, Python treats the `(5)` below as an integer in parentheses:

```python
tup = (5,)
print(type(tup))

x = (5)
print(type(x))

>>> <class 'tuple'>
>>> <class 'int'>
```

### Tuple assignment

Tuple of values can be assigned to a tuple of variables in a one line statement: 

```python
julia = ("Julia", "Roberts", 1967, "Duplicity", 2009, "Actress", "Atlanta, Georgia")
(name, surname, birth_year, movie, movie_year, profession, birth_place) = julia
print(name)

>>> Julia
```

 **!!! ALERT!!! Both tuples must have equal amount of elements**

Tuple on the left can be only variable, but on the right can hold values of variables (previously assigned to something). It is very useful for swapping values for variables:

```python
(a,b) = (b,a)
```

### Tuples as Return Values

A function (which can only return a single value), can create a single tuple holding multiple elements.

```python
def circleInfo(r):
    """ Return (circumference, area) of a circle of radius r """
    c = 2 * 3.14159 * r
    a = 3.14159 * r * r
    return (c, a)

print(circleInfo(10))

>>> (62.8318, 314.159)
```

