# Python Iterators: A Step-By-Step Introduction
I love how beautiful and clear Python’s syntax is compared to many other programming languages.

Let’s take the humble for-in loop, for example. It speaks for Python’s beauty that you can read a Pythonic loop like this as if it was an English sentence:
```
numbers = [1, 2, 3]
for n in numbers:
    print(n)
```
But let’s take things step by step. Just like decorators, iterators and their related techniques can appear quite arcane and complicated on first glance. So we’ll ease into it.

In this tutorial you’ll see how to write several Python classes that support the iterator protocol. They’ll serve as “non-magical” examples and test implementations you can build upon and deepen your understanding with.

We’ll focus on the core mechanics of iterators in Python 3 first and leave out any unnecessary complications, so you can see clearly how iterators behave at the fundamental level.

I’ll tie each example back to the for-in loop question we started out with. And at the end of this tutorial we’ll go over some differences that exist between Python 2 and 3 when it comes to iterators.

Ready? Let’s jump right in!

## Python Iterators That Iterate Forever
We’ll begin by writing a class that demonstrates the bare-bones iterator protocol in Python. The example I’m using here might look different from the examples you’ve seen in other iterator tutorials, but bear with me. I think doing it this way gives you a more applicable understanding of how iterators work in Python.

Over the next few paragraphs we’re going to implement a class called Repeater that can be iterated over with a for-in loop, like so:
```
repeater = Repeater('Hello')
for item in repeater:
    print(item)
```

Like its name suggests, instances of this Repeater class will repeatedly return a single value when iterated over. So the above example code would print the string Hello to the console forever.

To start with the implementation we’ll define and flesh out the Repeater class first:
```
 class Repeater:
    def __init__(self, value):
        self.value = value

    def __iter__(self):
        return RepeaterIterator(self)
```
On first inspection, Repeater looks like a bog-standard Python class. But notice how it also includes the __iter__ dunder method.

What’s the RepeaterIterator object we’re creating and returning from __iter__? It’s a helper class we also need to define for our for-in iteration example to work:
```
class RepeaterIterator:
    def __init__(self, source):
        self.source = source

    def __next__(self):
        return self.source.value
```
Again, RepeaterIterator looks like a straightforward Python class, but you might want to take note of the following two things:
1- In the __init__ method we link each RepeaterIterator instance to the Repeater object that created it. That way we can hold on to the “source” object that’s being iterated over.

2- In RepeaterIterator.__next__, we reach back into the “source” Repeater instance and return the value associated with it.        