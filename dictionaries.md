## 12. Dictionaries (mutable)

### Definitions

> All of the compound data types we have studied in detail so far — **strings**, **lists**, and **tuples** — are sequential collections. 
>
> The items in the collection are ordered from left to right and they use integers as indices to access the values they contain.

**Dictionaries** are a different kind of collection. They are Python’s built-in **mapping type**. A map is an unordered, associative collection.

The association, or mapping, is from a **key**, which can be any immutable type, to a **value**, which can be any Python data object.

#### Create dictionary

**dictionary literal**

```python
new_dictionary = {} 
eng2sp = {'three': 'tres', 'one': 'uno', 'two': 'dos'}

eng2sp = {}
eng2sp['one'] = 'uno'
eng2sp['two'] = 'dos'
eng2sp['three'] = 'tres'
```

**dictionary constructor**

```python
dict() # not talked about yet
```

#### Work with data in a dictionary

```python
eng2sp = {'three': 'tres', 'one': 'uno', 'two': 'dos'}
value = eng2sp['two']
>>> dos
```

`del` statement removes a key-value pair from a dictionary

```python
inventory = {'apples': 430, 'bananas': 312, 'oranges': 525, 'pears': 217}
del inventory['pears']

>>> {'apples': 430, 'bananas': 312, 'oranges': 525}
```

updating value (from above)

```python
inventory['bananas'] = inventory['bananas'] + 200
```

number of items:

```python
len(inventory)
>>> 3
```

### Methods

| Method | Parameters | Description                              |
| ------ | ---------- | ---------------------------------------- |
| keys   | none       | Returns a view of the keys in the dictionary |
| values | none       | Returns a view of the values in the dictionary |
| items  | none       | Returns a view of the key-value pairs in the dictionary. It is (key, value) tuple. |
| get    | key        | Returns the value associated with key; None otherwise |
| get    | key,alt    | Returns the value associated with key; alt otherwise |

[More methods in python documentation](https://docs.python.org/3/library/stdtypes.html#mapping-types-dict)

**!!! Alert view** looks like a list but is not of list type. Must be converted. 

```python
inventory = {'apples': 430, 'bananas': 312, 'oranges': 525, 'pears': 217}

for akey in inventory.keys():
   print("Got key", akey, "which maps to value", inventory[akey])

>>> Got key apples which maps to value 430
>>> Got key bananas which maps to value 312
>>> Got key oranges which maps to value 525
>>> Got key pears which maps to value 217
```

```python
print(type(inventory.keys()))
>>> <class 'dict_keys'>

ks = list(inventory.keys())
print(ks)
print(type(ks))
>>> ['apples', 'bananas', 'oranges', 'pears']
>>> <class 'list'>
```

#### Skipping .keys()

```python
for akey in inventory.keys():
   print("Got key", akey, "which maps to value", inventory[akey])

### is equivalent to

for akey in inventory:
   print("Got key", akey, "which maps to value", inventory[akey])
```

It is used so often, it got implemented as default looping, and for loop iterating over a dictionary implicitly iterates over its keys.

#### .keys() vs .items() 

```python
for (k,v) in inventory.items():
    print("Got", k, "that maps to", v)

### is equivalent to

for k in inventory:
    print("Got", k, "that maps to", inventory[k])
```

### Prevent no key in dictionary

Hand-coded:

```python
inventory = {'apples': 430, 'bananas': 312, 'oranges': 525, 'pears': 217}
print('apples' in inventory)
print('cherries' in inventory)

if 'bananas' in inventory:
    print(inventory['bananas'])
else:
    print("We have no bananas")
```

Built-in way:

```python
inventory = {'apples': 430, 'bananas': 312, 'oranges': 525, 'pears': 217}

print(inventory.get("apples"))		# 430
print(inventory.get("cherries"))	# None

print(inventory.get("cherries", 0))	# 0
```

### Aliasing and Copying

Because dictionaries are mutable, you need to be aware of aliasing.

```python
opposites = {'up': 'down', 'right': 'wrong', 'true': 'false'}
alias = opposites

print(alias is opposites)

alias['right'] = 'left'
print(alias is opposites)

>>> True
>>> True
```

Make copies instead

```python
acopy = opposites.copy()
acopy['right'] = 'left'    
print(alias is opposites)

>>> False
```

### Sparse Matrices

A matrix is a two dimensional collection, typically thought of as having rows and columns of data:

![sparse matrix](images/sparse.png)

Represented in code as:

```python
matrix = [[0, 0, 0, 1, 0],
          [0, 0, 0, 0, 0],
          [0, 2, 0, 0, 0],
          [0, 0, 0, 0, 0],
          [0, 0, 0, 3, 0]]
```

But the awful amount of zeros is making it really inefficient. In fact, only three of the data values are nonzero. This type of matrix has a special name. It is called a [sparse matrix](http://en.wikipedia.org/wiki/Sparse_matrix).

An alternative representation is to use a dictionary. 

```python
matrix = {(0, 3): 1, (2, 1): 2, (4, 3): 3}
```

Access data with the default value assigned:

```python
matrix = {(0, 3): 1, (2, 1): 2, (4, 3): 3}
print(matrix.get((0,3), 0))
print(matrix.get((1,3), 0))

>>> 1
>>> 0
```

To display the matrix of size `n:m` loop the range, asking for each key.

```python
matrix = {(0, 3): 1, (2, 1): 2, (4, 3): 3}

rows = 5
columns = 5

for row in range(rows):
    current_row = []
    for column in range(columns):
        current_row.append(matrix.get((row, column), 0))
    print(current_row)
    
>>> [0, 0, 0, 1, 0]
>>> [0, 0, 0, 0, 0]
>>> [0, 2, 0, 0, 0]
>>> [0, 0, 0, 0, 0]
>>> [0, 0, 0, 3, 0]
```

Matrix does not have to be a square!