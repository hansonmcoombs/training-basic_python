Basic Python Objects, Variables, and Operators
==============================================

Variables
------------
# how to assign variables
# pointers vs objects

Numbers: Integers and Floats
--------------------
there are four main ways to portray numeric values in python - integers, long, floats, and complex.

an Integers is as you would expect, a number without a decimal point (e.g. 1, 2, 3, or -5000).  Very big integers are
stored by python in another way that has enough precision (called a long).  While the behind the scenes programming is
a bit different for longs, 99% of the time it makes no difference.

Floats on the other hand are numbers with a decimal point.  We won't really talk about complex numbers here, but if you
are really keen have a look at {#todo find a complex number option to link to}

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

    x + y	# sum of x and y
    x - y	# difference of x and y
    x * z	# product of x and z
    z / x	# quotient of z and x	(1)
    z // x	# (floored) quotient of z and x	(5)
    z % x	# remainder of z / x	(4)
    -x	#x negated
    +x	#x unchanged
    abs(z)	#absolute value or magnitude of x
    int(y)	#y converted to integer	(2)
    long(y)	#y converted to long integer	(2)
    float(x)  #x converted to floating point
    z ** x	#z to the power x


+---------+--------+
|Opperation | action|
+==========+========+
|x + y	| sum of x and y|
+---------+--------+
|x - y	| difference of x and y|
+---------+--------+
|x * y	| product of x and y|
+---------+--------+
x / y	| quotient of x and y	(1)|
+---------+--------+
x // y	| (floored) quotient of x and y	(5)|
+---------+--------+
x % y	| remainder of x / y	(4)|
+---------+--------+
|-x	|x negated|
+---------+--------+
|+x	| x unchanged|
+---------+--------+
|abs(x)	| absolute value or magnitude of x|
+---------+--------+
|int(x)	|x converted to integer	(2)|
+---------+--------+
|long(x)	| x converted to long integer	(2)|
+---------+--------+
|float(x) |	x converted to floating point|
+---------+--------+
|x ** y|	x to the power y|
+---------+--------+




Boolean
--------
# True, False operations and order of operations

Strings
---------


