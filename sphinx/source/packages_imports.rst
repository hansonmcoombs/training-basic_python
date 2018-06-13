Using Packages in python
=========================

External packages
------------------

We've already talked about installing specific packages, but simply installing a package on your computer does not allow
you to use the package in a script - you also need to import the package. This is very much in line with every other
scripting language and it provides two main functions: 1) it is explicit what packages are used for a given script and
2) it lowers the overhead of any script (you don't need to load in everything you've installed). Before we explain how
to import things, we need to have a quick discussion around namespaces.

A namespace is a naming convention that python uses to avoid ambiguity. Simply put, a namespace is a name given
to a collection of functions and variables. You can imagine it, abstractly, as family names. Consider the Howard's and
the Smiths

+---------+-------+
+Howard   | Smith +
+=========+=======+
+Larry    | Bill  +
+---------+-------+
+Moe      | Larry +
+---------+-------+
+Curly    | Carl  +
+---------+-------+

Both families ahve a member called Larry, if I just tell you I'm going to see Larry, you don't know who I mean. Instead
if I say I'm going over to the Howard's then it's clear which Larry I mean. For a python example, both builtin
python and the package Numpy have functions called min, max, and abs. Without a namespace there would be no way
to distinguish between them, but if I say min vs numpy.min it's clear as day.

Let's look at some examples of how to import packages using the package math, which unsurprisingly has a whole host of
mathematical functions and objects. There are three ways to import specific packages:

1. Importing selected items from a package to the current namespace

    .. ipython:: python

        from math import pi  # just import pi
        print(pi)

    This is useful if you know you only need a few select functions from a package, but does run the risk of overwriting a
    function that is already present, for example *from numpy import min* would overwrite the builtin min function.

2. Importing everything from a package to the current namespace

    .. ipython:: python

        from math import *  # import everything
        print(pi)

    This is really bad form in most scripts as you run a serious risk that you'll overwrite something you don't want to.
    Also if you import everything from multiple packages it is less clear where a given function or variable came from.

3. Importing a namespace (with or without a name change)

    .. ipython:: python
        :suppress:

        import math

    .. code:: python

        import math

    .. ipython:: python

        print(math.pi)

        import math as m  # import the namespace math and change the name to m
        print(m.pi)

    This is probably the most common and is more efficient (for the coder) if many functions are going to be used, it
    also eliminates the overwrite concern.

Importing from your own python scripts
----------------------------------------

You can also import functions and variables from scripts that you have already developed. Consider the following file
tree:

::

    project
    ├── functions
    │   ├── __init__.py
    │   ├── interpolation_techs
    │       ├── __init__.py
    │       └── geostatistical.py
    │   └── lsr_calc.py
    ├── examples
    │   ├── rainfall_interpolation.py
    │   └── lsr.py

As long as the project folder is in your PYTHONPATH (more on this in a second) you can import objects from any script (.py)
that is in any python module.  A python module simply a folder that contains an *__init__.py* file. The file may be
completely blank, or it can hold a set of imports for initialising the module. For our purposes we'll assume that the
*__init__.py* file is blank, but you can find more information about what can be contained in inits `here <http://mikegrouchy.com/blog/2012/05/be-pythonic-__init__py.html>`_

Looking at the project tree above (remember the project folder is in your PYTHONPATH), you can import objects as follows:

.. code:: python

    # import a mythical function that converts potential evapotranspiration (et) to actual et from lsr_calc.py
    from functions.lsr_calc import pet_to_aet

    # import a mythical function that does kriging interpolation from geostatistical.py
    from functions.interpolation_techs.geostatistical import krig

Note that you cannot import anything from the examples folder as it does not have an *__init__.py* file.

Adding a folder to the PYTHONPATH
-----------------------------------

On Windows
^^^^^^^^^^^^

1. Open Explorer.
2. Right-click *'Computer'* in the Navigation Tree Panel on the left.
3. Select *'Properties'* at the bottom of the Context Menu.
4. Select *'Advanced system settings'*
5. Click *'Environment Variables...'* in the Advanced Tab
6. Under 'System Variables':
    1. If it does not exist add: **PYTHONPATH**
    2. Append the path to your project separating paths with *;* as follows

.. code::

    C:\Users\Documents\project;C:\another-library

You will now be able to import objects from projects in every python script that you write on your computer.

Within python
^^^^^^^^^^^^^^^

You can also add a folder to your python path in a script before you import from that folder as follows:

.. code:: python

    folder_path = "C:/Users/Documents/project"  # path to the project folder
    import sys  # a built in package which helps you access the pythonpath
    sys.path.append(folder_path)  # adds the folder to the pythonpath
    from functions.lsr_calc import pet_to_aet  # now you can import as usual

