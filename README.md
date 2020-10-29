# Tasks assessment 2020

This repository is used for the tasks assessments given during the Fundamentals of Data Analysis module on Higher Diploma in Data Analytics course from GMIT.\
Here I will explain how I came to the solution of given tasks, reference the sources I researched for solving the problems and list the technologies I used for creating and testing the code.


## Task 1

"Write a Python function called counts that takes a list as input and returns a dictionary of unique items in the list as keys and the number of times each item appears as values. So, the input ['A', 'A', 'B', 'C', 'A'] should have output {'A': 3, 'B': 1, 'C': 1} . Your code should not depend on any module from the standard library or otherwise. You should research the task first and include a description with references of your algorithm in the notebook." [1]

First step in solving this problem is creating a list by user input. User is instructed to separate items of the list with whitespace.

```python
    list = input("Enter the list items separated with spaces: ").split()
```

Since user input is recognised as *string*, unless it is specified differently, it was neccesary to adjust that input into list. [2] \
Part of code that does that is method *split()* used for splitting a string into a list. [3]

Syntax for *split()* method is:

```python
    str.split(separator, maxsplit)
```
where parameters are *separator* and *maxsplit*. \
Parameter *separator* is a delimiter; if not specified, it's default is *None* which means it recognises any whitespace as a separator.\
Parameter *maxsplit* is a number which specifies how many number of times the split needs to be done; it's default is *-1* which means there is no limit in number of splits.

Default values were used in solving the task.

After watching the lecture on mapping, the idea was to solve the problem with map. After research, conclusion is that the list comprehension is simpler and easier to write and read the code.\
 Since the output in the task needs to be a dictionary, similar way to list comprehension is dictionary comprehension, which is used in the solution.  

```python
    dict = {i:list.count(i) for i in list}
```



**Sources used for researching mapping and comprehension**

* [TechBeamers. Python map().](https://www.techbeamers.com/python-map-function/)
* [Thispointer.Python : map() function explained with examples.](https://thispointer.com/python-map-function-explained-with-examples/)
* [Stackoverflow. Map list onto a dictionary.](https://stackoverflow.com/questions/1993840/map-list-onto-dictionary)
* [Stackoverflow. Make map return a dictionary.](https://stackoverflow.com/questions/4863406/make-map-return-a-dictionary)
* [RealPython. Python's map(): Processing Iterables Without a Loop.](https://realpython.com/python-map-function/)
* [RealPython. Coding With Pythonic Style: Replacing map().](https://realpython.com/python-map-function/#coding-with-pythonic-style-replacing-map)
* [Stackoverflow. List comprehension vs map.](https://stackoverflow.com/questions/1247486/list-comprehension-vs-map)
* [Stackoverflow. How can I count the ocurrences of a list item.](https://stackoverflow.com/questions/2600191/how-can-i-count-the-occurrences-of-a-list-item)
* [RealPython. When to Use a List Comprehension in Python.](https://realpython.com/list-comprehension-python/)
* [Medium. How to count occurrences in a Python list.](https://medium.com/better-programming/how-to-count-occurrences-in-a-python-list-f799072538b3)
* [GeeksForGeeks. Python map vs list comprehension.](https://www.geeksforgeeks.org/python-map-vs-list-comprehension/)


### References
[1] [Ian McLoughlin, "Tasks 2020"](https://learnonline.gmit.ie/mod/url/view.php?id=102071) \
[2] [RealPython. Basic Input, Output, and String Formatting in Python.](https://realpython.com/python-input-output/)\
[3] [w3schools.com. Python string split() method](https://www.w3schools.com/python/ref_string_split.asp)




