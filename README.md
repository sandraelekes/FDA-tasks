# Tasks assessment 2020

This repository is used for the tasks assessments given during the Fundamentals of Data Analysis module on Higher Diploma in Data Analytics course from GMIT.\
Here I will explain how I came to the solution of given tasks, reference the sources I researched for solving the problems and list the technologies I used for creating and testing the code.

***
## **Table of contents**
* [Task 1](#task-1)
* [Task 2](#task-2)

***
## **Task 1**
***
"Write a Python function called counts that takes a list as input and returns a dictionary of unique items in the list as keys and the number of times each item appears as values. So, the input ['A', 'A', 'B', 'C', 'A'] should have output {'A': 3, 'B': 1, 'C': 1} . Your code should not depend on any module from the standard library or otherwise. You should research the task first and include a description with references of your algorithm in the notebook." [1]

### **Solution**
***

First step in solving this problem is creating a list by user input. User is instructed to separate items of the list with whitespace.

```python
    user_list = input("Enter the list items separated with spaces: ").split()
```

Since user input is recognised as *string*, unless it is specified differently, it was neccesary to adjust that input into list. [2] \
Part of code that does that is method *split()* used for splitting a string into a list.

Syntax for *split()* method is:

```python
    str.split(separator, maxsplit)
```
where parameters are *separator* and *maxsplit*. \
Parameter *separator* is a delimiter; if not specified, it's default is *None* which means it recognises any whitespace as a separator.\
Parameter *maxsplit* is a number which specifies how many number of times the split needs to be done; it's default is *-1* which means there is no limit in number of splits. [3] [4]

Default values were used in solving the task.

Next step is defining a function called *counts()* that takes that list as an input and return a dictionary.

Syntax for defining a function is:

``` python
    def function_name(parameters):
        "function docstring"
        statement1
        statement2
        ...
        return [expression]
```
The keyword for defining a function is *def* and it is followed by identifier, which is the name of the function, and parentheses.\
There can be one or more parameters inside parentheses and they are usually input parameters or arguments, but it is also possible to define parameters.\
The colon symbol *:* after parentheses starts an intended block of code.\
First statement in the code block is *"function docstring"*. This statement is optional and it represents a string that explains the functionality of the function.\
*Statement1* and *statement2* represent body of the function - tasks that need to be performed.\
Statement *return* exits a function and sends control back to caller. Argument *expression* is optional and it is *None* by default, but if it is defined, it's value is also returned to the caller. [5] [6]


Following the syntax for defining a function, function *counts()* was created.

``` python
    def counts(user_list):
        out_dict = {item:user_list.count(item) for item in user_list}
        return out_dict
    print(counts(user_list))
```
This function takes previously defined list as an input.

After watching the lecture on mapping, the idea was to solve the problem with map. After research, conclusion is that the list comprehension is simpler and easier to write and read the code.\
Since the output in the task needs to be a dictionary, dictionary comprehension is used in solution, which is similar to list comprehension.

Dictionary comprehension is similar to list comprehension. It's a concept that can be used to substitute for loops and lambda functions. [7] It creates dictionary by merging two sets of data which are, in this case, in the form of list. [8]
Syntax for dictionary comprehension is:

``` python
    {key:value for var in iterable}
```

*Key* and *value* can be any expression and evaluated once for each item in interable.\
*Var* takes items from an iterable one by one.\
*Iterable* is a collection like list, tuple and such. [9]

Dictionary comprehension for the task:
```python
    out_dict = {item:user_list.count(item) for item in user_list}
```
Our *value* in the code is *user_list.count(item)* which is based on *count(x)* method of list objects.
*list.count(element)* method has one parameter *element* and by definition it counts the number of occurances ot that element in the list. [10] 

Considering the syntax of dictionary comprehension, and definition of *list.count()* this part of code can be explained in this way:
with *item* (item in the list) as a key, number of ocurances is counted for every item *item* in the *user_list* (input from user).


**Sources used for researching mapping and comprehension**

* [TechBeamers. Python map().](https://www.techbeamers.com/python-map-function/)
* [Thispointer. Python : map() function explained with examples.](https://thispointer.com/python-map-function-explained-with-examples/)
* [Stackoverflow. Map list onto a dictionary.](https://stackoverflow.com/questions/1993840/map-list-onto-dictionary)
* [Stackoverflow. Make map return a dictionary.](https://stackoverflow.com/questions/4863406/make-map-return-a-dictionary)
* [RealPython. Python's map(): Processing Iterables Without a Loop.](https://realpython.com/python-map-function/)
* [RealPython. Coding With Pythonic Style: Replacing map().](https://realpython.com/python-map-function/#coding-with-pythonic-style-replacing-map)
* [Stackoverflow. List comprehension vs map.](https://stackoverflow.com/questions/1247486/list-comprehension-vs-map)
* [Stackoverflow. How can I count the ocurrences of a list item.](https://stackoverflow.com/questions/2600191/how-can-i-count-the-occurrences-of-a-list-item)
* [RealPython. When to Use a List Comprehension in Python.](https://realpython.com/list-comprehension-python/)
* [Medium. How to count occurrences in a Python list.](https://medium.com/better-programming/how-to-count-occurrences-in-a-python-list-f799072538b3)
* [GeeksForGeeks. Python map vs list comprehension.](https://www.geeksforgeeks.org/python-map-vs-list-comprehension/)


### **References**
[1] [Ian McLoughlin. "Tasks 2020".](https://learnonline.gmit.ie/mod/url/view.php?id=102071) \
[2] [RealPython. Basic Input, Output, and String Formatting in Python.](https://realpython.com/python-input-output/)\
[3] [w3schools.com. Python string split() method.](https://www.w3schools.com/python/ref_string_split.asp)\
[4] [Python.org. str.split().](https://docs.python.org/3.9/library/stdtypes.html#str.split)\
[5] [TutorialsTeacher. Python - User-Defined Functions.](https://www.tutorialsteacher.com/python/python-user-defined-function)\
[6] [Tutorialspoint. Python 3 - Functions.](https://www.tutorialspoint.com/python3/python_functions.htm)\
[7] [DataCamp. Python Dictionary Comprehension Tutorial.](https://www.datacamp.com/community/tutorials/python-dictionary-comprehension)\
[8] [Edpresso Team. What is dictionary comprehension in Python?](https://www.educative.io/edpresso/what-is-dictionary-comprehension-in-python)\
[9] [Learn by example. Python Dictionary Comprehension.](https://www.learnbyexample.org/python-dictionary-comprehension/)\
[10] [Finxter. Python List count().](https://blog.finxter.com/python-list-count/)

***
***
## **Task 2**


