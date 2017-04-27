## 10. Lists

A **list** is a sequential collection of Python data values, where each value is identified by an **index**. The values that make up a list are called its **elements**.

Lists are ordered collections of **anything**. The types of list elements can be of any kind, even other lists.

### Creating a list

Closing things in `[]` square brackets:

```python
[10, 20, 30, 40]
["spam", "bungee", "swallow"]
["hello", 2.0, 5, [10, 20]] 		# nested list
[] 									# empty list
a = ["a", 1] 						# variable holding a list 
print(a)							# passing list to functions as parameters
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

### Concatenation and Repetition (Multiplication)

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

This means we can change an item in a list by accessing it directly as part of the assignment statement. Using the **indexing operator** (square brackets) on the left side of an assignment, we can update one of the list items. 

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





* 1. ​
  2. ​
  3. ​
  4. ​
  5. ​
  6. ​
  7. ​
  8. ​
  9. Lists](https://runestone.launchcode.org/runestone/static/thinkcspy/Lists/Lists.html)
* [2. List Length](https://runestone.launchcode.org/runestone/static/thinkcspy/Lists/ListLength.html)
* [3. Accessing Elements](https://runestone.launchcode.org/runestone/static/thinkcspy/Lists/AccessingElements.html)
* [4. List Membership](https://runestone.launchcode.org/runestone/static/thinkcspy/Lists/ListMembership.html)
* [5. Concatenation and Repetition](https://runestone.launchcode.org/runestone/static/thinkcspy/Lists/ConcatenationandRepetition.html)
* [6. List Slices](https://runestone.launchcode.org/runestone/static/thinkcspy/Lists/ListSlices.html)
* [7. Lists are Mutable](https://runestone.launchcode.org/runestone/static/thinkcspy/Lists/ListsareMutable.html)
* [8. List Deletion](https://runestone.launchcode.org/runestone/static/thinkcspy/Lists/ListDeletion.html)
* [9. Objects and References](https://runestone.launchcode.org/runestone/static/thinkcspy/Lists/ObjectsandReferences.html)
* [10. Aliasing](https://runestone.launchcode.org/runestone/static/thinkcspy/Lists/Aliasing.html)
* [11. Cloning Lists](https://runestone.launchcode.org/runestone/static/thinkcspy/Lists/CloningLists.html)
* [12. Repetition and References](https://runestone.launchcode.org/runestone/static/thinkcspy/Lists/RepetitionandReferences.html)
* [13. List Methods](https://runestone.launchcode.org/runestone/static/thinkcspy/Lists/ListMethods.html)
* [14. Append versus Concatenate](https://runestone.launchcode.org/runestone/static/thinkcspy/Lists/AppendversusConcatenate.html)
* [15. Lists and`for`loops](https://runestone.launchcode.org/runestone/static/thinkcspy/Lists/Listsandforloops.html)
* [16. Exercises](https://runestone.launchcode.org/runestone/static/thinkcspy/Lists/Exercises.html)

## 11. Lists, Continued

* [1. Using Lists as Parameters](https://runestone.launchcode.org/runestone/static/thinkcspy/ListsContinued/UsingListsasParameters.html)
* [2. Pure Functions](https://runestone.launchcode.org/runestone/static/thinkcspy/ListsContinued/PureFunctions.html)
* [3. Which is Better?](https://runestone.launchcode.org/runestone/static/thinkcspy/ListsContinued/WhichisBetter.html)
* [4. Functions that Produce Lists](https://runestone.launchcode.org/runestone/static/thinkcspy/ListsContinued/FunctionsthatProduceLists.html)
* [5. List Comprehensions](https://runestone.launchcode.org/runestone/static/thinkcspy/ListsContinued/ListComprehensions.html)
* [6. Nested Lists](https://runestone.launchcode.org/runestone/static/thinkcspy/ListsContinued/NestedLists.html)
* [7. Strings and Lists](https://runestone.launchcode.org/runestone/static/thinkcspy/ListsContinued/StringsandLists.html)
* [8.`list`Type Conversion Function](https://runestone.launchcode.org/runestone/static/thinkcspy/ListsContinued/listTypeConversionFunction.html)
* [9. Tuples and Mutability](https://runestone.launchcode.org/runestone/static/thinkcspy/ListsContinued/TuplesandMutability.html)
* [10. Tuple Assignment](https://runestone.launchcode.org/runestone/static/thinkcspy/ListsContinued/TupleAssignment.html)
* [11. Tuples as Return Values](https://runestone.launchcode.org/runestone/static/thinkcspy/ListsContinued/TuplesasReturnValues.html)
* [12. Glossary](https://runestone.launchcode.org/runestone/static/thinkcspy/ListsContinued/Glossary.html)
* [13. Exercises](https://runestone.launchcode.org/runestone/static/thinkcspy/ListsContinued/Exercises.html)



