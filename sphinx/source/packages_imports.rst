Using Packages in python
=========================

External packages
------------------

We've already talked about installing specific packages, but simply installing a package on your computer does not allow
you to use the package in a script - you also need to import the package. This is very much in line with every other
scripting language and it provides two main functions: 1) it is explicit what packages are used for a given script and
it lowers the overhead of any script (you don't need to load in everything you've installed). Before we explain how to
import things, we need to have a quick discussion around namespaces.

A namespace is a naming convention that python uses to avoid ambiguity. Simply put, a namespace is a name given
to a collection of functions and variables. You can imagine it, abstractly, as family names.

+---------+-------+
+Howard   | Smiths+
+=========+=======+
+Larry    | Bill  +
+---------+-------+
+Moe      | Larry +
+---------+-------+
+Curly    | Curtis+
+---------+-------+

If you say you're talking about the Howard's then it's clear which Larry you mean. For a python example both built in
python and the package Numpy have functions called min, max, and abs. Without a namespace there would be no way
to distinguish between them, but if I say min vs numpy.min it's clear as day.

Let's look at some examples of how to import packages using the package math, which unsurprisingly has a whole host of
mathematical functions. There are three ways to import specific packages:

1. importing selected items from a package to the current namespace

.. ipython:: python

    from math import pi
    print(pi)

2. importing everything from a package to the current namespace

.. ipython:: python

    from math import *
    print(pi)

3. importing a namespace (with or without a name change)

.. ipython:: python
    import math
    print(math.pi)

    import math as m  # import the namespace math and change the name to m
    print(m.pi)

1) is useful if you know you only need a few select functions from a package, but does run the risk of overwriting a
function that is already present, for example from numpy import min would overwrite the builtin min function. 2) is
really bad form in most scripts as you run a serious risk that you'll overwrite something you don't want to.  Also if
you import everything from multiple packages it is less clear where a given function or variable came from. 3) is
probably the most common and is more efficient (for the coder) if many functions are going to be used, or if there is an
overwrite concern.


Importing from your own python scripts
----------------------------------------

You can also import functions and variables from scripts that you have already developed.

# python path... update in script or in windows
how to import things from your own packages...
# python 3 makes it tricky to use anything other than absolute paths.
