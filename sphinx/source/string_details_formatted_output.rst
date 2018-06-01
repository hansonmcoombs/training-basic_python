Strings, the good, the bad, and the ugly
==========================================

String indexing
-----------------

The character components of a string can be accessed the same way that a list can be.  Each character as a positional
assignment, so for example:

+---+---+--+--+--+--+--+--+--+--+---+
|-11|-10|-9|-8|-7|-6|-5|-4|-3|-2|-1 |
+---+---+--+--+--+--+--+--+--+--+---+
|h  |e  |l |l |o |  |w |o |r |l |d  |
+---+---+--+--+--+--+--+--+--+--+---+
|0  |1  |2 |3 |4 |5 |6 |7 |8 |9 |10 |
+---+---+--+--+--+--+--+--+--+--+---+

You can index and slice a string just like you would a list, so for example:

.. ipython:: python

    my_string = 'hello world'
    my_string[0]
    my_string[-1]
    my_string[3:9]


String operators & functions
-------------------

Strings have access to two operators *+* and *, and the behaviour is just like lists, so:

.. ipython:: python

    my_string = 'spam'
    my_string + 'eggs'
    my_string * 5

There are a number of useful functions associated with string objects. Python strings are case sensitive so:

.. ipython:: python

    'spam' == 'SPAM'
    'spam' != 'SPAM'

Luckily there are a number of functions to assist with various capitalisation choices that you may want:

.. ipython:: python

    my_string = 'your mother was a haMster and your father smElt of elderberries'
    my_string.lower() # all characters to lower case
    my_string.upper() # all characters to upper case
    my_string.capitalize() # first character to upper
    my_string.title() # the first character of each word capitalized

There are also functions to help break up and put together strings.

.. ipython:: python

    print(my_string)
    # .split() splits the sting into a list of stings by removing the characters specified (a space in this case)
    temp = my_string.split(' ')
    type(temp)
    print(temp)
    # ''.join() takes as list of strings and joins them together with the characters in proceeding string
    '-'.join(temp)


Finally there are some useful functions to remove characters from strings:

.. ipython:: python

    # ''.strip() removes characters from the beginning and/or end of a sting, the default is a space
    test = '*********lunch*lunch***********'
    test.strip('*')

    # ''.replace(old, new) finds all instances of the old string and replaces it with the new string
    test.replace('lunch', 'dinner')

Formatted output
-----------------

In python there is an elegant way to create formatted string outputs using the *''.format()* method. The basic premise
of the format method is that you pass the arguments in the function into specific places into the proceeding string.
So for example:

.. ipython:: python

    # passing arguments('spam' and 'eggs') by position into the {}
    print("I don't like {} or {}".format('spam', 'eggs'))

    # passing arguments by keywords into the {}
    print("""{p} ran away. {adv} ran away away.
    When danger reared it’s ugly head, he {adv} turned his tail and fled.
    {p} turned about and gallantly he chickened out""".format(p='Brave Sir Robin', adv='Bravely'))

    # you can pass anything into the .format method that can be passed to the print function
    my_list = [1,2,3]
    my_dict = {'Bert': 'Ernie'}
    my_number = 42
    my_new_string = 'like lists : {}, dictionaries: {}, and numbers: {}.'.format(my_list, my_dict, my_number)
    print(my_new_string)

Passing values back into a string is useful enough, but the .format() method of strings gives significantly more control
over how the object is transformed into a sting. Below we'll cover the most commonly used formatting options for environmental
scientists, but For a deeper dive into the full capabilities of python formatted output,
check out this lovely `tutorial <https://pyformat.info/>`_.

.. ipython:: python

    '{:4d}'.format(42)  # at least 4 digits, padded with spaces
    '{:04d}'.format(42)  # at least 4 digits, padded with zeros
    '{:4d}'.format(42666666) # note that this can go beyond 4 digits

    '{:6.2f}'.format(3.14159265)  # at least 6 digits, padded with spaces, with exactly 2 digits after the decimal point
    '{:06.2f}'.format(3.14159265)  # as above but padded with zeros

