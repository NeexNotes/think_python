## 10. Lists \(mutable\)

A **list** is a sequential collection of Python data values, where each value is identified by an **index**. The values that make up a list are called its **elements**.

Lists are ordered collections of **anything**. The types of list elements can be of any kind, even other lists.

### Creating a list

Closing things in `[]` square brackets:

```python
[10, 20, 30, 40]
["spam", "bungee", "swallow"]
["hello", 2.0, 5, [10, 20]]         # nested list
[]                                     # empty list
a = ["a", 1]                         # variable holding a list 
print(a)                            # passing list to functions as parameters
```

A list within another list is said to be **nested**. The inner list is a **sublist**.

### Length - just the outer!

```python
alist =  ["hello", 2.0, 5, [10, 20]]
print(len(alist))
print(len(['spam!', 1, ['Brie', 'Roquefort', 'Pol le Veq'], [1, 2, 3]]))
>>> 4
>>> 4
```

### Accessing elements

```python
numbers = [17, 123, 87, 34, 66, 8398, 44]
print(numbers[2])
print(numbers[9 - 8])
print(numbers[-2])
print(numbers[len(numbers) - 1])
```

Just like strings!

```python
list = [1,2,3, [1,2]]
```

accessing can be chained!

```python
list[3][0]
>>> 1
```

And just like strings, we can **slice**.

```python
a_list = ['a', 'b', 'c', 'd', 'e', 'f']
print(a_list[1:3])
print(a_list[:4])
print(a_list[3:])
print(a_list[:])

>>> ['b', 'c']
>>> ['a', 'b', 'c', 'd']
>>> ['d', 'e', 'f']
>>> ['a', 'b', 'c', 'd', 'e', 'f']
```

### `in` or `not in` list AKA. List membership

Just like strings:

```python
fruit = ["apple", "orange", "banana", "cherry", [1,2]]

print("apple" in fruit)
print("pear" in fruit)

>>> True
>>> False
```

BUT only outer list!

```python
print(1 in fruit)
>>> False
```

### Concatenation and Repetition \(Multiplication\)

```python
fruit = ["apple", "orange", "banana", "cherry"]
print([1, 2] + [3, 4])
print(fruit + [6, 7, 8, 9])

print([0] * 4)
print([1, 2, ["hello", "goodbye"]] * 2)

>>> [1, 2, 3, 4]
>>> ['apple', 'orange', 'banana', 'cherry', 6, 7, 8, 9]
>>> [0, 0, 0, 0]
>>> [1, 2, ['hello', 'goodbye'], 1, 2, ['hello', 'goodbye']]
```

### Memory location

```python
alist = [4, 5, 6]
id(alist)
>>> 140135490300424
```

### MUTABILITY

Unlike strings, lists are **mutable**.

This means we can change an item in a list by accessing it directly as part of the assignment statement. Using the **indexing operator** \(square brackets\) on the left side of an assignment, we can update one of the list items.

An assignment to an element of a list is called **item assignment**.

### Change items

```python
fruit = ["banana", "apple", "cherry"]
fruit[0] = "pear"
print(fruit)

>>> ['pear', 'apple', 'cherry']
```

Change slice on the go:

```python
alist = ['a', 'b', 'c', 'd', 'e', 'f']
alist[1:3] = ['x', 'y']
print(alist)

>>> ['a', 'x', 'y', 'd', 'e', 'f']
```

### Remove items

We can also **remove** elements from a list by **assigning the empty list** to them.

```python
alist = ['a', 'b', 'c', 'd', 'e', 'f']
alist[1:3] = []
print(alist)

>>> ['a', 'd', 'e', 'f']
```

Using slices to delete list elements can be awkward and therefore error-prone. Python provides an alternative that is more readable. The `del` statement removes an element from a list by using its position.

```python
a = ['one', 'two', 'three']
del a[1]
print(a)

>>> ['one', 'three']
```

**Alert!** `del` causes a runtime error if the index is out of range. But so does reassignment using `[]`.

### Insert items

```python
alist = ['a', 'd', 'f']
alist[1:1] = ['b', 'c']
print(alist)
alist[4:4] = ['e']
print(alist)

>>> ['a', 'b', 'c', 'd', 'f']
>>> ['a', 'b', 'c', 'd', 'e', 'f']
```

### Clone \(copy\) list

```python
a = [81, 82, 83]
b = a[:] 
print(a == b)
print(a is b)

>>> True
>>> False
```

### List Methods

```python
mylist = [5, 12, 27, 3, 12]            # [5, 12, 27, 3, 12]
mylist.append(5)                    # [5, 12, 27, 3, 12, 5]
mylist.insert(1, 12)                # [5, 12, 12, 27, 3, 12, 5]
mylist.index(3)                        # 4
mylist.count(5)                        # 2
mylist.reverse()                    # [5, 12, 3, 27, 12, 12, 5]
mylist.sort()                        # [3, 5, 5, 12, 12, 12, 27]
mylist.remove(5)                    # [3, 5, 12, 12, 12, 27]
lastitem = mylist.pop()                # [3,5,12,12,12]
print(lastitem)                        # 27
```

The word **mutator** means that the list is changed by the method but nothing is returned \(actually `None` is returned\). A **hybrid** method is one that not only changes the list but also returns a value as its result. Finally, if the result is simply a return, then the list is unchanged by the method.

| Method | Parameters | Result | Description |
| --- | --- | --- | --- |
| append | item | mutator | Adds a new item to the end of a list |
| insert | position, item | mutator | Inserts a new item at the position given |
| pop | none | hybrid | Removes and returns the last item |
| pop | position | hybrid | Removes and returns the item at position |
| sort | none | mutator | Modifies a list to be sorted |
| reverse | none | mutator | Modifies a list to be in reverse order |
| index | item | return idx | Returns the position of first occurrence of item |
| count | item | return ct | Returns the number of occurrences of item |
| remove | item | mutator | Removes the first occurrence of item |

[More in documentation](https://docs.python.org/3/library/stdtypes.html#sequence-types-str-bytes-bytearray-list-tuple-range)

It is important to remember that methods like `append`, `sort`, and `reverse` all return `None`. Do not use them for reassignment !!!

### List traversal

```python
fruits = ["apple", "orange", "banana", "cherry"]

for fruit in fruits:     # by item
    print(fruit)
```

```python
fruits = ["apple", "orange", "banana", "cherry"]

for position in range(len(fruits)):     # by index
    print(fruits[position])
```

Since lists are mutable, it is often desirable to traverse a list, modifying each of its elements as you go.

```python
numbers = [1, 2, 3, 4, 5]
print(numbers)

for i in range(len(numbers)):
    numbers[i] = numbers[i] ** 2

print(numbers)

>>> [1, 2, 3, 4, 5]
>>> [1, 4, 9, 16, 25]
```

### Using lists as parameters

Functions which take lists as arguments and change them during execution are called **modifiers** and the changes they make are called **side effects**. Passing a list as an argument actually passes a reference to the list, not a copy of the list.

```python
def doubleStuff(aList):
    """ Overwrite each element in aList with double its value. """
    for position in range(len(aList)):
        aList[position] = 2 * aList[position]

things = [2, 5, 9]
print(things)
doubleStuff(things)
print(things)

>>> [2, 5, 9]
>>> [4, 10, 18]
```

### Pure function

> A **pure function** does not produce side effects.

It communicates with the calling program only through **parameters** \(which it does not modify\) and a **return value**.

```python
def doubleStuff(a_list):
    """ Return a new list in which contains doubles of the elements in a_list. """
    new_list = []
    for value in a_list:
        new_elem = 2 * value
        new_list.append(new_elem)
    return new_list

things = [2, 5, 9]
print(things)
things = doubleStuff(things)
print(things)
```

### Functional programming

Anything that can be done with **modifiers** can also be done with **pure functions**. In fact, some programming languages only allow pure functions. There is some evidence that programs that use pure functions are faster to develop and less error-prone than programs that use modifiers. Nevertheless, modifiers are convenient at times, and in some cases, functional programs are less efficient.

In general, we recommend that you write pure functions whenever it is reasonable to do so and resort to modifiers only if there is a compelling advantage. This approach might be called a **functional programming style**.

### List Comprehensions

List comprehensions are concise ways to create lists. The general syntax is:

```python
[<expression> for <item> in <sequence> if  <condition>] # if is optional.
```

```python
mylist = [1,2,3,4,5]
yourlist = [item ** 2 for item in mylist]
print(yourlist)

>>> [1, 4, 9, 16, 25]
```

using the `if` clause \(assuming you have access to `is_prime()` function:

```python
[num for num in range(2,n) if is_prime(num)]
```

#### List comprehension explained with an example: 
**Problem**: 
You have to print a list of all possible coordinates given a 3D grid where the sum of x,y,z is != N

for x=y=z=1 and N=2  
**output**:  
`[[0, 0, 0], [0, 0, 1], [0, 1, 0], [1, 0, 0], [1, 1, 1]]` 

Standard loop solution:
```python
x = 1
y = 1
z = 1
n = 2
grid = []

for a in range(x + 1):
    for b in range(y + 1):
        for c in range(z + 1):
            if a + b + c != n:
                grid.append([a, b, c])
print(grid)
>>> [[0, 0, 0], [0, 0, 1], [0, 1, 0], [1, 0, 0], [1, 1, 1]]
```
List comprehension solution
```python
x = 1
y = 1
z = 1
n = 2

print([[a,b,c] for a in range(x+1) for b in range(y+1) for c in range(z+1) if a+b+c != n])
```
### Lists and strings

```python
string = "Hello you, how are you?"
string.split()                             # by default breaks on space
```

An optional argument called a **delimiter** can be used to specify which characters to use as word boundaries. The delimiter does not appear in the results.

```python
song = "The rain in Spain..."
wds = song.split('ai')
print(wds)

>>> ['The r', 'n in Sp', 'n...']
```

Joining back \(after some changes\):

```python
wds = ["red", "blue", "green"]
glue = ';'
s = glue.join(wds)
print(s)
print(wds)

print("***".join(wds))
print("".join(wds))

>>> red;blue;green
>>> ['red', 'blue', 'green']
>>> red***blue***green
>>> redbluegreen
```

#### Type conversion. To list. `list()`

```python
xs = list("Crunchy Frog")
print(xs)

>>> ['C', 'r', 'u', 'n', 'c', 'h', 'y', ' ', 'F', 'r', 'o', 'g']
```

It is not legal to use the `list`conversion function on any argument that is not a sequence.

* `split` will break a string into a list of “words”
* `list` will always break it into a list of characters



