Conditional Statements
=======================

Conditional statements in python allow code to do different things in different circumstances.  These statements use the
*if*, *elif*, and *else* keywords. The easiest way to show conditional statements in python is through a simple example:

.. ipython:: python

    # what will i do?
     raining = True
     if raining:  # start of the if statement
         # indent exactly 4 spaces
         print('clean the garage')  # what I will do if the condition is true
    else: # start of the otherwise (else) clause
         # indent exactly 4 spaces
         print('weed the garden')  # what I will do if raining == False

In human speak this says that if it is raining (which it is), I'll clean the garage otherwise (else), I'll weed the garden.
Python identifies that something is in the if clause (or the else clause) by the indentation of the code. After the if
statement the code is indented by exactly 4 spaces be for the actions (print('clean the garage')). While this may seem
pedantic, at the end of the day it creates much clearer, human readable code that is less prone to typos and other errors.

Before we can get onto more complex conditional statements we need to talk about the conditional operators:

+------------+---------------------------+---------------------+
| Operator   | meaning                   | applies to          |
+============+===========================+=====================+
| ==         | equals                    | most objects        |
+------------+---------------------------+---------------------+
| !=         | does not equal            | most objects        |
+------------+---------------------------+---------------------+
| <          | less than                 | numbers             |
+------------+---------------------------+---------------------+
| >          | greater than              | numbers             |
+------------+---------------------------+---------------------+
| <=         | less than or equal        | numbers             |
+------------+---------------------------+---------------------+
| >=         | greater than or equal     | numbers             |
+------------+---------------------------+---------------------+
| all()      | all elements True         | iterable of boolean |
+------------+---------------------------+---------------------+
| any()      | any element True          | iterable of boolean |
+------------+---------------------------+---------------------+

Armed with these comparisons and the *elif* keyword we can create much more complicated conditional statements.
*elif* is an abbreviation for else if and allows the user to specify more conditions, For example:

.. ipython:: python

    weather = 'sunny'
    # what will I do?
    if weather == 'raining':
        print('clean the garage')
   elif weather == 'sunny':
        print('go to the beach')
   elif weather == 'raining hellfire':
        pass  # the python keyword pass will move past the conditional statement without doing anything
   else:
        print('weed the garden')
    print('ok then')

