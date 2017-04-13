## Simple Python Data
### Values and Data Types

**value** - is one of the fundamental things — like a word or a number — that a program manipulates. We often refer to these values as **objects** and we will use the words value and object interchangeably.

**objects** are classified into different **classes** or **data types**:

* integers (4,5,6,7, natural numbers)
* floats (4.3, floating-point numbers)
* strings (text, any text, even number in text) - single or double quote => absolutely no diff in Python

### Type conversion functions

**int** - converting to integer, either float, or string that contains number, always cuts down

**float** - converts to float, int or string, containing number. Adding `.0`  to into and conversing str as needed

**str** - turns integers and floats into strings

```python
print("2345", int("2345"))
> 2345 2345
print(17, int(17))
> 17 17
print(int("23bottles")
> ValueError: invalid literal for int() with base 10: '23bottles' on line 5

print(float("123.45"))
> 123.45
print(type(float("123.45")))
> <class 'float'>

print(str(17))
> 17
print(str(123.45))
> 123.45
print(type(str(123.45)))
> <class 'str'>
```

### Variables

**Assignment statements** create new variables and also give them values to refer to.

```
message = "What's up, Doc?"
n = 17
pi = 3.14159
```

> **assignment token**`=`  should not be confused with **equality** 

#### state snapshot

This kind of figure, known as a **reference diagram**, is often called a **state snapshot** because it shows what state each of the variables is in at a particular instant in time. 

![state_snapshot](images/state_snapshot.png)

### Variable names and keywords

* can be arbitrarily long

* contain both letters and digits

* HAVE TO BEGIN with a letter or _underscore

* legal to use uppercase letters, by convention we don’t

* it is common to split words with an underscore `just_like_that`

* no $peci@l characters

* no **keywords** - keywords are Python syntax words. Sometimes modules have them too:

```python
and	as	assert	break	class	continue
def	del	elif	else	except	exec
finally	for	from	global	if	import
in	is	lambda	nonlocal	not	or
pass	raise	return	try	while	with
yield	True	False	None	 	 
```

### Statements and Expressions

A **statement** is an instruction that the Python interpreter can execute. 

* assignment statement
* `while`statements
* `for` statements
* `if` statements
* `import` statements
* (There are other kinds too!)

An **expression** is a combination of:
* values

* variables

* operators

* and calls to functions

Expressions need to be evaluated. If you ask Python to `print` an expression, the interpreter **evaluates** the expression and displays the result.





* [3. Variables](https://runestone.launchcode.org/runestone/static/thinkcspy/SimplePythonData/Variables.html)
* [4. Variable Names and Keywords](https://runestone.launchcode.org/runestone/static/thinkcspy/SimplePythonData/VariableNamesandKeywords.html)
* [5. Statements and Expressions](https://runestone.launchcode.org/runestone/static/thinkcspy/SimplePythonData/StatementsandExpressions.html)
* [6. Operators and Operands](https://runestone.launchcode.org/runestone/static/thinkcspy/SimplePythonData/OperatorsandOperands.html)
* [7. Input](https://runestone.launchcode.org/runestone/static/thinkcspy/SimplePythonData/Input.html)
* [8. Order of Operations](https://runestone.launchcode.org/runestone/static/thinkcspy/SimplePythonData/OrderofOperations.html)
* [9. Reassignment](https://runestone.launchcode.org/runestone/static/thinkcspy/SimplePythonData/Reassignment.html)
* [10. Updating Variables](https://runestone.launchcode.org/runestone/static/thinkcspy/SimplePythonData/UpdatingVariables.html)
* [11. Glossary](https://runestone.launchcode.org/runestone/static/thinkcspy/SimplePythonData/Glossary.html)
* [12. Exercises](https://runestone.launchcode.org/runestone/static/thinkcspy/SimplePythonData/Exercises.html)


