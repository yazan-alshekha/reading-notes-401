# List Comprehensions in Python

List comprehensions provide a concise way to create lists.

It consists of brackets containing an expression followed by a for clause, then
zero or more for or if clauses. The expressions can be anything, meaning you can
put in all kinds of objects in lists.

The result will be a new list resulting from evaluating the expression in the
context of the for and if clauses which follow it.

The list comprehension always returns a result list.

If you used to do it like this:


```
new_list = []
for i in old_list:
    if filter(i):
        new_list.append(expressions(i))

```
You can obtain the same thing using list comprehension. Notice the append method has vanished!

`new_list = [expression(i) for i in old_list if filter(i)]`

**Syntax**
The list comprehension starts with a ‘[‘ and ‘]’, square brackets, to help you remember that the
result is going to be a list.

The basic syntax uses square brackets.

`[ expression for item in list if conditional ]`

This is equivalent to:

```
for item in list:
    if conditional:
        expression

```
Let’s break this down and see what it does.


```
new_list = [expression(i) for i in old_list if filter(i)]
```

**new_list**
The new list (result).

**expression(i)**
Expression is based on the variable used for each element in the old list.

**for i in old_list**
The word for followed by the variable name to use, followed by the word in the
old list.

**if filter(i)**
Apply a filter with an If-statement.

`new_range = [i * i for i in range(5) if i % 2 == 0]`

Which corresponds to:
`*result* = [*transform* *iteration* *filter* ]`


