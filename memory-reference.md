## Memory reference 

**Strings** are immutable so Python saves memory and points to the same memory location:

![stringreference](images/stringreference.png)

**Lists** are mutable so they refer to different location, but the immutable elements inside list will indeed point to the same locations.

![listreference](images/listreference.png)

### Aliasing

Since variables refer to objects, if we assign one variable to another, both variables refer to the same object:

```python
a = [81, 82, 83]
b = a
print(a is b)

>>> True
```

![listreference](images/aliasing.png)

Because the same list has two different names, `a` and `b`, we say that it is **aliased**. Changes made with one alias affect the other.

Although this behavior can be useful, it is sometimes unexpected or undesirable. In general, it is safer to avoid aliasing when you are working with mutable objects. Of course, for immutable objects, there’s no problem. That’s why Python is free to alias strings and integers when it sees an opportunity to economize.