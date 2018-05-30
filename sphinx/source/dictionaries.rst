Dictionaries
===============

What's in a dictionary
-----------------------

Another key basic object in python is the dictionary.  Dictionaries are iterables, but unlike lists (and tuples if you
got that far) values in a dictionary are indexed by a user specified key rather than a positional argument. the default
structure of a dictionary is {key: value}.  The value can be any object in python (numbers, strings, boolean, lists,
and so on).  Keys are a bit more proscriptive; the rules are a bit more complex, but for beginners it's normally enough
to know that numbers and strings are able to be keys.  For more details on exactly what python objects can be keys in a
dictionary see: `Why Lists Can't be Dictionary Keys <https://wiki.python.org/moin/DictionaryKeys>`_.
Note as of python version 3.6 dictionaries will remembers the order that the data was input, previously they were un-ordered.
Now for some examples:

.. ipython:: python

    my_dict = {'key': 'value'}
    my_dict

    # to access data from a dictionary you use brackets and the key
    my_dict['key']

    # it is possible to assign new values to a dictionary

    my_dict['new_key'] = 'new_value'
    my_dict['new_key']

    # it is also possible to overwrite existing keys
    my_dict['key'] = 'peanut butter'
    my_dict['key']

    # you can also create dictionaries from nest lists (or tuples) of key, value pairs and the dict() function:
    temp = [
            ['peanut butter', 'jam'],
            ['eggs', 'bacon'],
            ['muslie', 'milk']
            ]
    my_food = dict(temp)
    my_food
    my_food['eggs']

    # just like lists dictionaries have length
    len(my_food)  # returns the number of key, value pairs

    # the keyword *in* also works, but only looks in the dictionaries keys
    'eggs' in my_food
    'bacon' in my_food

Important dictionary functions
-------------------------------

Just like lists, dictionaries have a number of useful built in functions here we'll showcase the four most important -
*.update()*, *.keys()*, *.values()*, *.items()*

.. ipython:: python

    # .update adds the entries of a second dictionary to the first
    my_dict = {'Bert': 'Ernie'}
    another_dict = {'Sherlock Holmes': 'Watson', 'Batman': 'Robin'}
    my_dict.update(another_dict)
    my_dict

    # .keys(), .values(), .items() are all about accessing all of the keys, values,
    # and (key, value) pairs in a dictionary, respectively.
    # they are useful to see what's in your dictionary and for iteration which we'll talk about later
    my_dict.keys()
    my_dict.values()
    my_dict.items()
    # note that the behaviour of these functions are slightly different in python 2.7



