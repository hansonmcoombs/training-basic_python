Basic Python Objects, Variables, and Operators
==============================================

.. toctree::
   :maxdepth: 1
   :caption: prerequisites

    whatpython


Variables
------------
# how to assign variables
# pointers vs objects


Numbers: Integers and Floats
--------------------
there are four main ways to portray numeric values in python - integers, long, floats, and complex.

an Integers is as you would expect, a number without a decimal point (e.g. 1, 2, 3, or -5000).  Very big integers are
stored by python in another way that has enough precision (called a long).  While the behind the scenes programming is
a bit different for longs, 99% of the time it makes no difference and you can consider them equivalent.

Floats on the other hand are numbers with a decimal point.  We won't really talk about complex numbers here, but if you
are really keen, have a look at {#todo find a complex number option to link to}

.. ipython:: python

    type(1)
    type(1000000000000000)
    type(3.1415)
    type(3.)

There are a number of operations that you can do with numeric values:

.. ipython:: python

    x = 2
    y = 3.5
    z = -5

    x + y  # sum of x and y
    x - y  # difference of x and y
    x * z  # product of x and z
    z / x  # quotient of z and x	(1) (2)
    z // x  # (floored) quotient of z and x	(3)
    z % x  # remainder of z / x	(4)
    -x  # x negated
    +x  # x unchanged
    abs(z)  # absolute value or magnitude of z
    int(y)  # y converted to integer
    long(y)  # y converted to long integer
    float(x)  # x converted to floating point
    z ** x  # z to the power x

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

A boolean value in python is either True or False as with numeric data there a several basic operations that can
be preformed on boolean data

.. ipython::python

    True or False
    True or True
    True and True
    True and False
    not True
    not False

    all([True, True, False]) # this uses a list, which will be described in the next section
    any ([True, False, False]) # this uses a list, which will be covered in the next section

order of operations also applies to boolean operations, so:

.. ipython::python

    True and (True or False)
    False or (True and False)

boolean values can be converted to integers and floats

.. ipython::python:
    int(True)
    int(False)


Strings
---------

Strings are made up of different characters (e.g. a, b, c, %, &, ?, etc.).  Every sentence ever written can be
considered as a string. You can make strings in a number of ways by wrapping characters ' and " so for example:

.. ipython::python
    x = 'my string'
    y = "also my string"
    z = "my string can contain quotes 'like this one'"

    x
    y
    z

    x = """
    triple " or ' can define a string that splits
    a number of lines
    like this
    """
    x


    # numbers can be represented as strings
    x = '5'
    x

    # and stings can be converted to floats and ints
    int(x)
    float(x)

    # though python isn't smart enough to convert everything to a numeric value and throws an exception
    x = 'five'
    int(x)


There are many different operators and ways to manage strings, for more information please see # link to string details


The print function
-------------------

up to now in order to see the contents of a variable we have simply been calling the variable.  This works fine in an
interactive python environment, but when running a python script from start to finish you need the print function.
print function is easy to use and will simply print the variable.  so for instance:

.. ipython::python

    x = 'some string'
    print(x)

    print(1,1,2,2,3)
