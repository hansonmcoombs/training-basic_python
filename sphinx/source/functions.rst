Functions in Python
=====================

What is a function?
-----------------------

A function is a block of organised, contained, reusable code. You can imagine using the same block of code, copying and
pasting is again and again in your script. What are the chances that in one of those copy and pastes you'll make a
mistake - almost 100%! One of the
basic principles in good programming is “do not to repeat yourself” both to avoid mistakes, but also to make code more
human readable. Functions allow you to wrap up code into a package that you can use again and again or allow you to use
other people's work to make the job quicker. During the course so far, we've already showcased a number of functions,
like the print() function. We have also used methods which are functions that are tied to a specific object instance,
like *[].append()*.

Before we get into creating your own functions, let's get a better handle on the structure of functions in python.
The general framework of a function is:

.. code:: python

    def function_name(*args, **kwargs):
        outdata = some actions
        return outdata

In human speak.  The def keyword lets python know you're creating a function named *function_name*, which takes as inputs
some *args* and *kwargs*. An arg is a positional argument, who's value is defined by the position in the function call, so
in this fictional function call:

.. code:: python

    new_val = function_name(1, 2, trend_type=3)

1 is the first arg, 2 is the second arg.  3 on the other hand is a kwarg or keyword argument; the value of this
argument is defined by the keyword trend_type.
Following the : in the function definition, there is some indented code that typically does some action and creates a
new variable. The end of the function is typically marked by the *return* keyword.  This tells python to create a
variable (new_val) and point it to the object
that was defined as outdata inside the function. We need to return the object of outdata because as a general rule variables
created outside a function are not accessible inside a function unless they are passed in as arguments,
and those created inside a function are only accessible outside the function if they are explicitly passed out of the function by the keyword *return*.

Understanding function documentation
-------------------------------------

There are heaps of already developed functions that probably do almost exactly what you need to do, but in order to
use them you need to understand what an existing function does and it's quirks. The best source of knowledge for this
is the function documentation of a given function. It can take a bit
of time to get good at interpreting documentation, so let's make a start of it. To start we'll look at the
the built in function to enumerate iterables *enumerate()*.
Original documentation is `here <https://docs.python.org/3/library/functions.html#enumerate>`_, but it is included here as well:

**enumerate(iterable, start=0)**

    Return an enumerate object. iterable must be a sequence, an iterator, or some other object which supports iteration.
    The __next__() method of the iterator returned by enumerate() returns a tuple containing a count
    (from **start** which defaults to 0) and the values obtained from iterating over **iterable**.

Let's look at what the first line of the documentation *enumerate(iterable, start=0)* is telling us.  First enumerate
can take up to two arguments (*iterable* and *start*), second we need to pass at least one argument (*iterable*) as it
has no default value (it isn't equal to anything), and third that if we do not pass a value for *start* it will be
set equal to 0.

The body of the text explains what the function does (creates an object, which for our purposes can be converted to a
list of tuples that contain a number, starting from start) It also gives more details on the arguments (in this case that
iterable, must be some object that supports iteration). So armed with this knowledge are you surprised by the result of:

.. ipython:: python

    my_list = ['a','b','c']

    # remember the list() here is just being used to get away from the unnecessary
    # complexity of the enumerate object
    list(enumerate(my_list, start=10)) # FYI the space after the comma and no spaces between the '=' is pep8 standard

    # above we passed the arguments as show in the documentation
    # we can also pass everything as kwargs in any order we choose
    list(enumerate(iterable=my_list, start=10))
    list(enumerate(start=10, iterable=my_list))

    # or everything as args, but it will break if we shift the order
    list(enumerate(my_list, 10))




Let's look at one more, the built in print function.  The actual print function documentation can be found `here <https://docs.python.org/3/library/functions.html#print>`_,
but it's also copied below:

**print(*objects, sep=' ', end='\n', file=sys.stdout, flush=False)**

    Print objects to the text stream file, separated by sep and followed by end. sep, end, file and flush, if
    present, must be given as keyword arguments.

    All non-keyword arguments are converted to strings like str() does and written to the stream, separated by **sep**
    and followed by **end**. Both **sep** and **end** must be strings; they can also be None, which means to use the
    default values. If no objects are given, print() will just write end.

    The **file** argument must be an object with a write(string) method; if it is not present or None, sys.stdout will be
    used. Since printed arguments are converted to text strings, print() cannot be used with binary mode file objects.
    For these, use file.write(...) instead.

    Whether output is buffered is usually determined by file, but if the **flush** keyword argument is true, the stream
    is forcibly flushed.

    Changed in version 3.3: Added the flush keyword argument.

Let's look at the *objects in the first line of the documentation. This conceptually can be described as that all
positional arguments passed to print will be treated the same way. The keyword arguments
work just like they would in enumerate, but because there is *objects they obviously have to be passed as kwarg.

.. ipython:: python

    print(1,2,3,4,5,6)
    print(1,2,3,4,5,6, sep='!', end='ok\n') # the \n is a new line so the output prints normally

The final word of wisdom about function documentation is to treat it a bit like a puzzle.  If you don't quite understand
what a function does, spend some time playing with it in a console. See how it reacts to different inputs, try to break
it, and if you still can't understand what's going on it's time to check google and stack overflow.

Creating your own function in python
-------------------------------------

So we've talked a lot about using functions that others have build, but what about creating your own.  If you find
yourself copying and pasting code a lot, it's probably time to make a function.  My personal guideline is that if I've
used the same bit of code, with or without minor tweaks, three times, then it's time to package it up as a function.
Looking back at the basic structure of a function:

.. code:: python

    def function_name(*args, **kwargs):
        outdata = some actions
        return outdata


Defining your own is not that challenging. As an example let's define a function to convert temperature in fahrenheit to
celsius or kelvin:

.. ipython:: python

    # defining the function
    def fahrenheit_to_ck(temp, out_c=True):
        """
        convert temperature in degrees fahrenheit to celsius or kelvin
        :param temp: the temperature in fahrenheit as float
        :param out_c: boolean, if True convert to celsius, if False kelvin
        :return: temperature in c or k, float
        """
        c = (temp - 32) * 5 / 9
        k = c + 273.15
        if out_c:
            return c
        else:
            return k


.. ipython:: python
    # Now to use the function
    print(fahrenheit_to_ck(451))  # use the default and return celsius
    print(fahrenheit_to_ck(451, False)) # return kelvin instead

The *def fahrenheit_to_ck(temp, out_c=True):* tells python that a function called fahrenheit_to_ck is being created,
that it takes two arguments (*temp*, *out_c*) and that *out_c* has a default value of *True*.  The name of you function
should ideally be short (this one is pushing it), but descriptive, made of lowercase letters separated with underscores
where needed for clarity. The next few lines wrapped in triple quotation marks is the docstring. The docstring is in
built documentation for the function.  It's not necessary, but it is **highly** encouraged.  It helps anyone else
(including future you) understand what your function does. With the docstring it becomes easy to understand what the
argument *out_c* does. After you define a function in your script you can use it anywhere below the function definition
in your script.  For this reason, and for convention it is best to put function definitions at the top of any script.
You can import your function to use in other scripts, but that will be covered in a future :doc:`lesson <packages_imports>`

using *args and **kwargs
--------------------------

When you are looking at other peoples code you may find function calls that include one or more *s.  This is simply using
the *args and **kwargs format.  let's look at an example:

.. ipython:: python

    things_to_print = ['Spam', 'Spam', 'Spam', 'egg', 'and Spam'] # the args, must be iterable, typically a tuple, though a list also works
    how_to_print = {'sep':'-', 'end':'!\n'} # the kwargs, must be dictionary

    # simple printing
    print(things_to_print)

    # using *args
    print(*things_to_print)

    # using *args and **kwargs
    print(*things_to_print, **how_to_print)

So what is happening here?  The * in front of things_to_print tells python to take all of the values out of the iterable
(in this case a list) and pass them as positional arguments (e.g. the first item in the list becomes the first positional
argument and so on.  Note that you are no longer printing a list when using * in front of things_to_print. Remember that kwargs are
defined by a keyword and a value, which is not so different than a dictionary.  Here how_to_print has keys that exaclty
match the keywords of the print function (*sep*, *end*) and has the values to be used as the values of those keyword
arguments. the **how_to_print, simply tells python to use the keys and values of the dictionary to set the function
kwargs.
