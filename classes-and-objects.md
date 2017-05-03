## 13. Classes and Objects – Basics

Object-oriented programming (OOP) is a programming paradigm based on the concept of **"objects"**, which may contain data, in the form of fields, often known as **attributes**; and code, in the form of procedures, often known as **methods**. 

A feature of objects is that an object's procedures can access and often modify the data fields of the object with which they are associated (objects have a notion of "this" or "self").

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

