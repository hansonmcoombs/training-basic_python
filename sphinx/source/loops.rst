Loops in Python
=================

Ever been in the position where you have to do the same thing again, and again, and again.  It's painful and it feels
like there must be a better way.  There is, it's called a loop.

For loops in python
--------------------

The main loop that environmental scientists will use is a for loop.  The standard format for a for loop is:

.. code::python
    for i in iterable:
        action

let's break that down.  The iterable could be any python iterable or iterator (for now don't worry about the difference),
for instance a list.  Python will then create a variable (i) pointing to the first object in the list. Next python will then take some
action that is in the indented (4 spaces again) line of code.  After all the action code if completed python will then
set i to the second item in the list and repeat. A simple working example is:

.. ipython:: python

    >>> menu = ['Egg and Spam', # the iterable
    ...         'Egg, bacon and Spam',
    ...         'Egg, bacon, sausage and Spam',
    ...         'Spam, bacon, sausage and Spam',
    ...         'Spam, egg, Spam, Spam, bacon and Spam',
    ...         'Spam, Spam, Spam, egg and Spam',
    ...         'Spam, Sausage, Spam, Spam, Spam, Bacon, Spam, Tomato and Spam',
    ...         'Spam, Spam, Spam, Spam, Spam, Spam, baked beans, Spam, Spam, Spam and Spam']
    >>> for dish in menu:  # dish is the new variable
    ...     print(dish)  # print is the action
    ... print("I don't like spam!")

Useful builtins for for loops
------------------------------

Python has a number of builtin functions to assist iteration in for loops.  First is the range function which can be
used with 1-3 arguments to generate a sequence of integers. The sequence is held in a special object built for iteration,
but we can easily transform it into a list to give an idea of what is in the range

.. ipython:: python
    list(range(10)) # the integers from zero up to, but not including 10
    list(range(5, 11)) # the integers from 5 up to, but not including 11
    list(range(5, 26, 5])) # every 5th integer from 5 up to, but not including 26

    # the range function in action
    >>> for i in range(2,11,2):
    ...     print( i * 10)

The second is the zip function, which combines the elements of n equal length iterables together so that they can be
accessed at the same time

.. ipython:: python

    data1 = ['batman', 'bert', 'calvin']
    data2 = ['robin', 'ernie', 'hobbes']
    list(zip(data1,data2))

    # using the zip function in a for loop is easy
    for lead, sidekick in zip(data1, data2):
        print('{} & {}'.format(lead, sidekick)

In this example rather than the for loop creating 1 new variable it creates two (lead, sidekick) for the two components
of the zip object. You can zip togeather as many iterables a you need.  This examples also uses the .format function of
strings which is explained :doc:`here <string_details_formatted_output>`

The enumerate function is very similar to the zip function.  It essentially numbers the elements of the iterable
passed to it.

.. ipython:: python
    list(enumerate(data2))

    >>> for i, sidekick in enumerate(data2):
    ...     print('{} of {}'.format(i+1, len(data2)))
    ...     print(sidekick)


Lastly in the :doc:`lesson on dictionaries <dictionaries>` we mentioned the *.items()* function of the dictionary which
makes it easy to iterate through a dictionaries keys and values.

    my_dict = {'peanut butter': 'jam', 'eggs': 'bacon', 'muslie': 'milk'}
    for key, value in my_dict.items():
        print('{} is the key to {}'.format(key, value))

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

