The Python List
================

What's a list
---------------

One of the most fundamental objects in python is the list.  A list simply holds multiple objects, these can be of any
type. A list can be generated in two ways:

.. ipython:: python:

    # 1) with the [ ]
    my_list = [1, 2, 'some value', True]

    # 2) by converting some other datatype (an iterable) to a list with the list function
    my_other_list = list((1, 2, 3, 4, 5))  # this uses a tuple, which

    # a list can even hold other lists (nesting)
    my_nested_list = [[1, 2], [3, 4], [5, 6]]


length, indexing, and slicing
-------------------------------

You'll notice in the example above that we mentioned an iterable.  While it's not strictly the definition you can think
of an iterable as any sort of object that is a container for multiple objects.  The number of objects in an iterable
like a list is also known as the length of the list.  Unsurprisingly there is a python function to get the length of an
iterable like a list called *len()*

.. ipython:: python:

    my_list
    len(my_list) # using the lists defined above
    my_other_list
    len(my_other_list)

    # note for nested lists it will only give the length of the outermost list
    len(my_nested_list)

Great, I've but my very important data into a list, but how on earth can I get it out?  Through indexing and slicing.
Indexing is getting out a single item in the list, while slicing is getting out a subset of the list. Python is a zero
based indexing language.  That's a big phrase to say that the first (or more accurately the zeroth) item is given a
position index of 0, so for example *my_list*:

+------------+------------+-----------+---------------+-----------+
| Item       | 1          | 2         | 'some value'  | True      |
+------------+------------+-----------+---------------+-----------+
| Position   |0           | 1         |    2          |     3     |
+------------+------------+-----------+---------------+-----------+


.. ipython:: python:

    my_list

    # to index things use brackets []
    my_list[0]
    my_list[3]

    # trying to index something that does not exist will raise an exception
    my_list[4]

    # to access items from a sublist in a nested list you use chained brackets
    my_nested_list
    my_nested_list[0][1] # returns the second item of the first list in my_nested_list

    # you can also access things from the back end of the list:
    my_list[-1] # the last item
    my_list[-2] # the second to last item

    # slicing uses brackets and a :

    my_list[0:2]  # everything from the zeroth item up to, but not including the 2nd item
    my_list[1:]  # everything from the first item up to and including the last item
    my_list[:3]  # everything from the first item up to, but not including the 3rd item

list specific functions
-------------------------

Almost every python object has some functions built into them that will act on the instance of the object.
these functions are accessed with a '.', e.g. my_var.some_function().  Lists are no different, here we'll showcase the
two most important functions associated with lists, *.append()* and *.extend()*:

.. ipython:: python:

    # .append() adds something to a list
    my_list = []  # create an empty list
    my_list.append(1)
    my_list
    my_list.append('my string')
    my_list
    my_list.append([1,2])
    my_list

Note that when you append a list to a list it creates a nested list. If instead you want to append all of the
values of an iterable (like a list) to another list then you need to use the *.extend()* function:

.. ipython:: python:

    my_list = []  # create an empty list
    my_list.extend([1,2,3,4])
    my_list

    # note if you try to pass a non-iterable to extend it will raise an exception
    my_list.extend(1)



