Loops in Python
=================

Ever been in the position where you have to do the same thing again, and again, and again.  It's painful and it feels
like there must be a better way.  There is, it's called a loop.

For loops in python
--------------------
The main loop that environmental scientists will use is a for loop.  The standard format for a for loop is:

for i in iterable:
    action

let's break that down.  The iterable could be any python iterable or iterator (more on this in a minute), for instance
a list.  Python will then create a variable (i) pointing to the first object in the list, python will then take some
action that is in the indented (4 spaces again) line of code.  After all the action code if completed python will then
set i to the second item in the list and repeat. A simple working example is:

.. ipython:: python



+------------+---------------------------+---------------------+
| for    | i                    | in |  iterable          |
| start loop | assign temporary variab
+============+===========================+=====================+
| ==         | equals                    | most objects        |

# for loop
# nested loops

Useful builtins for for loops
------------------------------
# talk about iterators vs iterables?
# for loop with .items from dictionary
# for loop with zip for multiple lists
# enumerate
# range

While loops in Python
----------------------
There is another type of loop in python called a while loop. A while loop continues to iterate until a condition becomes
 false. For environmental scientists, this loop isn't used that regularly, but it is important to at least know of it's
 existence.  More detailed information about the while loop can be found `here <https://www.tutorialspoint.com/python/python_while_loop.htm>`_.

.. ipython:: python

    >>> my_number = 0
    >>> while my_number < 3:
    ...     print(my_number)
    ...     my_number +=1

