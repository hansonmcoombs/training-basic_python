Basic Python Objects, Variables, and Operators
==============================================


Variables
------------

Everything in python can be considered to be either a variable an object or an operator.  An object can be everything
from a number, to function, to something more complex like a class.  For the moment let's not worry too much about
objects, in fact most of this course is about how to create and use the plethora of objects that exist in the
python language. Briefly an operator is something that does something to a variable or an object (e.g. =, +, -, *).
We'll talk about operators in a moment.  Instead for now let's focus on the variable in python.

A python variable is basically the name we give to an object in a script.  Assignment of a variable is simple using
the *=* operator:

.. ipython:: python

    x = 42  # the variable in this case is x and we have assigned the value of 42 to the variable

A variable can be named anything except one of the built in keywords of python.
To get a list of these keywords you can use the help function:

.. ipython:: python

    help('keywords')

While you can name a variable anything, some options are better than others. As previously mentioned style is important.
The PEP 8 standards suggest that variables should be lowercase, with words separated by underscores as necessary to
improve readability.  While PEP 8 isn't necessary, it is a really good habit to get into. It is also very important not
to give a variable the name of any of the builtin functions and variables, otherwise you cannot use the
builtin function again in your script. That said don't panic about knowing every builtin variable, most integrated development
editors will raise some sort of warning when you overwrite a builtin name. Also if you try to use a builtin function
again it will simply raise an exception, for example:

.. ipython:: python

    # now we'll be naughty and overwrite the help function, really don't do this...
    help = 42

    # if we try to use the help function it will raise an exception
    help('keywords')

if you make this mistake, fix it in your script and reload you interpreter.

Why did this happen? It has to do with how python assigns variables.  When we assigned the value of 42 to *x* above the
number 42 was created in the computer's memory and the variable *x* was pointed to that memory via a unique object ID.
python has a built in function id(), which allows us to see the this ID.  This is helpful as we can see how python
handles memory.  Take a look at the example below:

.. ipython:: python:

    x = 42
    id(x)
    y = x
    id(y)
    x = 15
    y
    id(x)
    id(y)


Note that when we set *y* = *x* all it did was point *y* to the same bit of computer memory that *x* is pointing to. When
we re-assigned *x* (to 15) it points at a different part of memory leaving *y* unchanged with a value of 42.  So when we
overwrote the help function above, all we did was point the variable *help* to a new object (42)

When an object is no longer in use (e.g. no variables are pointing to it) a part of python called the garbage collector
will remove the object from memory so your computer doesn't have too much on it's mind.


Numbers: Integers and Floats
-------------------------------------

There are three main ways to portray numeric values in python - integers, floats, and complex.

An Integers is as you would expect, a number without a decimal point (e.g. 1, 2, 3, or -5000).
Floats on the other hand are numbers with a decimal point.  We won't really talk about complex numbers here, but it is
useful to know that python can handle complex numbers.

.. ipython:: python

    type(1)
    type(3.1415)
    type(3.)

the type function in python tells you what type a given object or variable is.

There are a number of operations that you can do with numeric values:

.. ipython:: python

    x = 2
    y = 3.5
    z = -5
    x + y  # the sum of x and y
    x - y  # the difference of x and y
    x * z  # the product of x and z
    z / x  # the quotient of z and x (2)
    z // x  # the floored quotient of z and x (3)
    z % x  # the remainder of z / x
    abs(z)  # the absolute value of z
    int(y)  # the integer of y rounded down
    float(x)  # x converted to a float
    z ** x  # z to the power of x

    x = 42
    x += 60 # add 60 to x and assign the new value back to x
    x

    x = 10
    x *= 10 # multiply x by 10 and assign the new value back to x
    x

some notes on these operations:

1. You can mix numeric types. Where possible python tries to maintain the numeric type throughout the operation,
but it will change the type if needed (e.g. from int to float).
2. The behaviour of division in python 2.7 is different to python 3.6.  This course assumes python 3.6 see more `here <http://sebastianraschka.com/Articles/2014_python_2_3_key_diff.html#python-2-1>`_.
3. Floored means always towards - infinity so -1.1 floored is -2 and 1.9 floored is 1.
4. Order of operation applies to mathematical formulas in python as normal so:

.. ipython:: python

    5 / (3 + 2)
    4 ** (1 / 2)


Boolean
--------

A boolean value in python is either True or False (case sensitive). As with numeric data there a several basic
operations that can be preformed on boolean data

.. ipython:: python

    True or False
    True or True
    True and True
    True and False
    not True
    not False
    all([True, True, False]) # this uses a list, which will be described in the next section
    any ([True, False, False]) # this uses a list, which will be covered in the next section

order of operations also applies to boolean operations, so:

.. ipython:: python

    True and (True or False)
    False or (True and False)

Boolean values can be converted to integers and floats where True = 1 and False = 0

.. ipython:: python

    int(True)
    int(False)


Strings
---------

Strings are made up of different characters (e.g. a, b, c, %, &, ?, etc.).  Every sentence ever written can be
considered as a string. You can make strings in a number of ways by wrapping characters ' and " so for example:

.. ipython:: python

    x = 'my string'
    y = "also my string"
    z = "my string can contain quotes of the other type 'like this one'"
    x
    y
    z
    x = """
    triple " or ' can define a string that splits
    a number of lines
    like this
    """
    x  # \n is the symbol for new line.  \' is the symbol for '
    # numbers can be represented as strings
    x = '5'
    x
    # and number stings can be converted to floats and ints
    int(x)
    float(x)
    # though python isn't smart enough to convert everything to a numeric value and will raise an exception
    x = 'five'
    int(x)


There are many different operators and ways to manage strings, for more information please see
:doc: 'this chapter on strings <../string_details_formatted_output>'


The print function
-------------------

Up to now in order to see the contents of a variable we have simply been calling the variable.  This works fine in an
interactive python environment, but when running a python script from start to finish you need the print function.
The print function is easy to use and will simply print the variable, so for instance:

.. ipython:: python

    x = 'some string'
    print(x)
    print(1,1,2,2,3)
