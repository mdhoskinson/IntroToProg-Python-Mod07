
# Files, Exceptions, and Pickling

## Introduction
In this module, we learn about working with text files, structured error handling, and using markdown language. There are a handful of webpages for reference on pickling and exception handling as well as a review of those webpages. In addition, this document will act as a standard operating procedure for creating both Pickling python code and an Exception Handling python code. In addition, we are also now able to answer a number of questions related to pickling, exception handling, and GitHub webpages and Markdown language.

## Research
### Pickling in Python
Stack Overflow https://stackoverflow.com/questions/7501947/understanding-pickling-in-python
I appreciate Stack Overflow as a resource because it is real users, with real life examples, and questions.  This person basically said ‘I have an assignment on pickling but I have no idea what pickling is.’  The other great thing about Stack Overflow is that it is a community and you often get great answers and references for resources from the community as a whole. I have referenced Stack Overflow for other GIS issues and find that most of my questions are either answered or lead me to a resource that is helpful.

Python.org  https://docs.python.org/3/library/pickle.html#module-pickle
In the past, I have found Python.org to be a good resource.  But, I think for a beginner, the explanations and comparisons to other modules such as marshal and json is too advanced for a beginner and not helpful in understanding the basics of pickling.

Afternerd.com (by Karim)  https://www.afternerd.com/blog/python-pickle/
Alternatively to the Python.org site I discussed above, I found that this webpage blog was very helpful. Karim explained that pickling is the ‘serialization and deserialization of Python objects’ which is very jargony.  But, he then says,’ First, let’s understand what serialization and deserialization mean.’  He then went on to use an example and broke down a complex context for beginners into its basic parts.  He also used screen capture examples as well as humor which makes it enjoyable and approachable to read.  I will bookmark his page and plan to use this webpage as a reference.  However, I found that there wasn’t much information on this site on Exception Handling.

Synopsis https://www.synopsys.com/blogs/software-security/python-pickling/
This webpage wasn’t super helpful in learning how to pickle, but it did give a good overview of how to use it, the dangers of pickling, and best practices.

### Exception Handling in Python
Python.org https://docs.python.org/3/tutorial/errors.html
Conversely to my comment on Python.org on pickling, I found this webpage to be helpful.  It gave a basic explanation of Syntax errors and how understand them, and then moved into Exceptions and Handling Exceptions using the try except method and discussed classes.  I found the explanations and code examples clear and easy to understand.

StackExchange https://softwareengineering.stackexchange.com/questions/308503/handling-exceptions-i-dont-know-about
This is another site similar to Stack Overflow.  I really find the questions posed and the answers provided by a community is very helpful.  Often times users are able to phrase their questions and answers in lay-terms with not as much jargon.  

Programiz https://www.programiz.com/python-programming/exception-handling
I found this site very helpful.  The explanations of Exception in Python and the screen captures of both the code and the output were simple to follow.  The author explains the process in simple terms and is easy to follow.

Python-course.eu https://python-course.eu/python-tutorial/errors-and-exception-handling.php
This webpage includes a good description of what Exception Handling is in python as well as shows some examples.  It explains the use of a while loop.  It’s easy to follow and clearly written.


## Methods
### Pickling a groceries list
1.	Import the pickle module
2.	Declare your groceries list
3.	Open the groceries list and write a .dat (pickled) file using the ‘wb’ command (write binary).
4.	Dump the groceries into the pickle file and close the file.
5.	Open the groceries.dat pickled file using the ‘rb’ command (read binary).

Python pickling demo code in full: 
```
# ------------------------------------------------- #
# Title: Error Handling demo
# Description:  Pickling your groceries list demo
# ChangeLog: (Who, When, What)
# <Mellony Hoskinson> <5/25/2022> Created Script
# ------------------------------------------------- #

import pickle
groceries = ['banana', 'chicken', 'broccoli']
print (groceries)

# Data -------------------------------------------- #
strFileName = 'groceries.dat'
lstgroceries = []

# Processing -------------------------------------- #
def save_data_to_file(file_name, list_of_data):
    objFile = open(file_name, "wb")
    pickle.dump(list_of_data, objFile)
    objFile.close()

def read_data_from_file(file_name):
    file = open(file_name, "rb")
    list_of_data = pickle.load(file)
    file.close()
    return list_of_data

print (groceries)
```

Python pickling demo in command prompt:
https://github.com/mdhoskinson/IntroToProg-Python-Mod07/blob/main/docs/Pickling_cmd.png

### Excpetion Handling
Method: Create a while loop and use the try except method using the ValueError exception.  The ValueError exception is a built in function in Python and gets raised when a user gives an invalid value, typically used in a mathematical operation.

1.	Create a while True loop and start the exception with the try.  Declare the age variable as an integer and ask the user to enter their age.
2.	Using the ValueError exception function, if the user does not enter an integer, have it reply that they did not enter a valid integer and ask the user again to enter their age.
3.	When the user enters a valid age integer, print “Great, you successfully entered your age!”

Exception Handling python code in full:
```# ------------------------------------------------- #
# Title: Error Handling demo
# Description:  Error Handling demo using the ValueError exception
# ChangeLog: (Who, When, What)
# <Mellony Hoskinson> <5/25/2022> Created Script
# ------------------------------------------------- #

while True:
    try:
        age = input("Please enter your age: ")  # Asks user to enter their age
        age = int(age)  # Declares the age variable as an integer
        break
    except ValueError:
        print("That is not a valid interger ...")
print("Great, you successfully entered your age!")
```

Exception Handling python code run using the command line prompt:
https://github.com/mdhoskinson/IntroToProg-Python-Mod07/blob/main/docs/ErrorHandling_cmd.png

## Questions
1)	What are the benefits of putting built-in Python command into functions?
a)	Functions are blocks of code used to perform specific actions.  The benefits are improving readability of code and reducing duplication of code.

2)	What are the benefits of using structured error handling?
a)	Structured Error Handling allows you to create custom errors using try-except blocks.  This is handy for when you think human interaction may cause a problem.

3)	What are the differences between a text file and a binary file?
a)	A binary file stores data as 1s and 0s.  A text file interprets the 1s and 0s into human readable text characters.

4)	How is the Exception class used?
a)	Exception is a built-in python class used to hold information about an error.  Python automatically creates and Exception object when an error occurs.  The Exception object automatically fills with information about the error that caused the exception.

5)	How do you "derive" a new class from the Exception class?
a)	The Exception class is a base class that can be used to create derived classes.  Derived classes inherit data and functions from the base class that can be replaced and customized.

6)	When might you create a class derived from the Exception class?
a)	You may create a class that is derived from the Exception class to capture specific types of errors.

7)	What is the Markdown language?
a)	Markdown is an easy-to-read, easy-to-write syntax for formatting plain text.

8)	How do you use Markdown on a GitHub webpage?
a)	GitHub combines a syntax for formatting text called GitHub Flavored Markdown with a few unique writing features.  The markdown code is converted into a static HTML page using a conversion processing application called Jekyll.


## Summary
In this module, we learned about working with text files, structured error handling, and using markdown language. We googled and research a number of webpages for reference on pickling and exception handling and reviewed them for helpfulness. Using information from those webpages as a starting point, we created our own pickling python code and an exception handling python code. We also answered a number of questions related to pickling, exception handling, and GitHub webpages and Markdown language.  Finally, we posted this Word document to our Mod07 GitHub webpage using Markdown language.
