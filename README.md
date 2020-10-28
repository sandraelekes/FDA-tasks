# Tasks assessment 2020

This repository is used for the tasks assessments given during the Fundamentals of Data Analysis module on Higher Diploma in Data Analytics course from GMIT.\
Here I will explain how I came to the solution of given tasks, reference the sources I researched for solving the problems and list the technologies I used for creating and testing the code.


## Task 1

    Write a Python function called counts that takes a list as input and returns a dictionary of unique items in the list as keys and the number of times each item appears as values. So, the input ['A', 'A', 'B', 'C', 'A'] should have output {'A': 3, 'B': 1, 'C': 1} . Your code should not depend on any module from the standard library or otherwise. You should research the task first and include a description with references of your algorithm in the notebook.

First step in solving this problem is creating a list by user input. User is instructed to separate items of the list with whitespace.

```python
    list = input("Enter the list items separated with spaces: ").split()
```

Since user input is recognised as *string*, unless it is specified differently, it was neccesary to adjust that input into list. [1] Part of code that does that is method *split()* used for splitting a string into a list. [1]

Syntax for *split()* method is:

```python
    str.split(separator, maxsplit)
```
where parameters are *separator* and *maxsplit*. \
Parameter *separator* is a delimiter; if not specified, it's default is *None* which means it recognises any whitespace as a separator.\
Parameter *maxsplit* is a number which specifies how many number of times the split needs to be done; it's default is *-1* which means there is no limit in number of splits.

Default values were used in solving the task.






### References
[1] [RealPython. Basic Input, Output, and String Formatting in Python.](https://realpython.com/python-input-output/)\
[2] [w3schools.com. Python string split() method](https://www.w3schools.com/python/ref_string_split.asp)



