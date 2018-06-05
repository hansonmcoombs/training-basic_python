What is Python
================

The official description of python is:

    Python is an interpreted, object-oriented, high-level programming language with dynamic semantics. Its high-level
    built in data structures, combined with dynamic typing and dynamic binding, make it very attractive for Rapid
    Application Development, as well as for use as a scripting or glue language to connect existing components together.
    Python's simple, easy to learn syntax emphasizes readability and therefore reduces the cost of program maintenance.
    Python supports modules and packages, which encourages program modularity and code reuse. The Python interpreter and
    the extensive standard library are available in source or binary form without charge for all major platforms, and can
    be freely distributed.

All that to say that Python is an open-access programming language that is easy to read, easy to write and fast to develop.

Perhaps best described in XKCD by Randell Munroe:

.. figure:: img/python.png

A brief history of python
----------------------------

Guido Van Rossum published the first version of Python code (version 0.9.0) at alt.sources in February 1991. The
creation of python was heavily influenced by the development of the programming language ABC. Since then it as seen
explosive growth to become one of the most common programming languages in the world.

What about the name python? Guido van Rossum, the creator of Python wrote "Over six years ago, in December 1989, I
was looking for a 'hobby' programming project that would keep me occupied during the week around Christmas. My
office ... would be closed, but I had a home computer, and not much else on my hands. I decided to write an
interpreter for the new scripting language I had been thinking about lately: a descendant of ABC that would appeal to
Unix/C hackers. I chose Python as a working title for the project, being in a slightly irreverent mood
(and a big fan of Monty Python's Flying Circus)."

Python versions
-----------------

There are currently 3 main versions of python, though typically only two are actually being used.  The most recent
version of python is 3.6, but some packages only support the last stable version of python 2, which is 2.7.  There as
always some differences between different python versions, but for this course we are assuming that all anyone will ever
use is python 3.6.

Installing python
-------------------

There are a number of ways to install python, but the easiest and the way we are going to install it via Anaconda.
Anaconda is a free and open source distribution of python and has been build in a way to simplify package management.
There are two ways to install python from Anaconda either 1) simply install Anaconda, which has most of the packages
you may need or 2) install miniconda (a very light weight version) and then add the packages you need.

For this course we recommend installing miniconda and building an environment based on a default set of packages that
we find the most useful for environmental scientists. It's not nearly as complex as it sounds.

1. go to https://conda.io/miniconda.html and download the appropriate python 3.6 installer

2. download the env file.... #todo document with mike

3. some command #todo document with mike

This will give you a python environment which has most of the useful libraries for everything from simple data analysis
to geospatial and GIS programming.


Interactive python, running scripts and IDEs
---------------------------------------------

IDEs (just spyder?, no list a couple) #todo
git/downloading git

Philosophy of coding, The Zen of Python, and pep8
---------------------------------------------------

Philosophy of coding
^^^^^^^^^^^^^^^^^^^^^^^

making mistakes is the best option #todo
comments!!! #todo

The Zen of Python
^^^^^^^^^^^^^^^^^^^^

Long time Pythoneer Tim Peters succinctly channels the Benevolent Dictator for Life's guiding principles for Python's
design into 20 aphorisms, only 19 of which have been written down.

- Beautiful is better than ugly.
- Explicit is better than implicit.
- Simple is better than complex.
- Complex is better than complicated.
- Flat is better than nested.
- Sparse is better than dense.
- Readability counts.
- Special cases aren't special enough to break the rules.
- Although practicality beats purity.
- Errors should never pass silently.
- Unless explicitly silenced.
- In the face of ambiguity, refuse the temptation to guess.
- There should be one-- and preferably only one --obvious way to do it.
- Although that way may not be obvious at first unless you're Dutch.
- Now is better than never.
- Although never is often better than *right* now.
- If the implementation is hard to explain, it's a bad idea.
- If the implementation is easy to explain, it may be a good idea.
- Namespaces are one honking great idea -- let's do more of those!

Pep8
^^^^^^^

#todo
