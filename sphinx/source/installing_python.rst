Building Python on Your computer
==================================

.. contents::
   :local:
   :depth: 2

Installing python and packages
--------------------------------

Python itself is rather lightweight. It contains some basic objects, and a few basic builtin packages. Nevertheless
it is quite a powerful language off the shelf.  For this course you will not need anything beyond the basic builtin
python.

There are a number of ways to install python, but the easiest and the way we are going to install it via Anaconda.
Anaconda is a free and open source distribution of python and has been build in a way to simplify package management.
There are two ways to install python from Anaconda either 1) simply install Anaconda, which has most of the packages
you may need and many that you will never use or 2) install miniconda (a very light weight version) and then add
the packages you need when you need them.

For this course we recommend installing miniconda as that is all you need and we discuss this later.
As you progress it is good experience to start
creating environments for your projects. In the long run it will save you time as you will not need to fight through
dependency issues (where one packaged depends on a specific version of another).

Packages are really the ace in the hole when it comes to python.  There are tens of thousands of packages that have
been developed to make programming easier. Complex statistical analysis?, check; interactive data visualisation?, check.
Basically if you need to do something, there's probably a package for that. For this course you will not be using any
packages that are not already built into python. That said as soon as you begin really doing work in python you'll use
packages galore.

In order to use packages, you have to
install them. At the end of the day the definitive expert on how to install a given package is that's package website,
but most packages that you will be interested in using can be easily installed with either pip or conda which is discussed below

Using python environments
-----------------------------

Can you imagine working on different projects, each needing a different set of packages, and perhaps some of them
requiring conflicting versions. Sounds like a nightmare. Using conda, rather than setting up one bloated python build
to try and do everything you are better off building a number of virtual python environments.

A virtual python environment is both a python build and a number of packages.  This build has a dedicated name, can
host specific versions of a package, and even specific versions of python (e.g. 2.7 or 3.6).  You can import and export
virtual python environments as lightweight text files, which makes collaborating even easier. In addition to
collaboration there are a couple of advantages to working in this style:

1. Reproducibility and clarity. When you finish up your project you can include an environment file and everyone will know exactly what you used to make your code.
2. Dependencies. You don't need to worry about competing dependencies ever again, you know that your code will run.
3. Safeguard from depreciation.  You won't need to worry about dusting off some code only to realise that it won't run because some key function was depreciated.

The instructions below on how use a conda environments are a simplified version of the instructions given `here <https://conda.io/docs/user-guide/tasks/manage-environments.html>`_.
You can read through the instructions, but they here more as a guide if/when you need them. For instructions on how to
create the recommended python environment for this course, please skip on to :ref:`this section <course-env>`.

Setting up virtual environments with conda
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Use the Terminal or an Anaconda Prompt for the following steps.

#. To create an environment:

   .. code::

      conda create --name myenv

   NOTE: Replace ``myenv`` with the environment name.

#. When conda asks you to proceed, type ``y``:

   .. code::

      proceed ([y]/n)?

This creates the myenv environment in ``/envs/``. This
environment uses the same version of Python that you are
currently using, because you did not specify a version.

To create an environment with a specific version of Python:

.. code-block:: bash

      conda create -n myenv python=3.6

.. _env-yml:

Creating an environment from an environment.yml file
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Use the Terminal or an Anaconda Prompt for the following steps.

#. Create the environment from the ``environment.yml`` file:

   .. code::

      conda env create -f environment.yml

The first line of the ``yml`` file sets the new environment's
name. The ``environment.yml`` can also be the explicit path to the .yml file.
 For details see :ref:`Creating an environment file manually
<create-env-file-manually>`.

.. _activate-env:

Activating an environment
^^^^^^^^^^^^^^^^^^^^^^^^^^

To activate an environment:

* On Windows, in your Anaconda Prompt, run ``activate myenv``

* On macOS and Linux, in your Terminal Window, run ``source activate myenv``

Conda prepends the path name ``myenv`` onto your system command.


Deactivating an environment
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

To deactivate an environment:

* On Windows, in your Anaconda Prompt, run ``deactivate``

* On macOS and Linux, in your Terminal Window, run ``source deactivate``

Conda removes the path name ``myenv`` from your system command.

TIP: In Windows, it is good practice to deactivate one
environment before activating another.


.. _determine-current-env:

Determining your current environment
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Use the Terminal or an Anaconda Prompt for the following steps.

By default, the active environment---the one you are currently
using---is shown in parentheses () or brackets [] at the
beginning of your command prompt::

  (myenv) $

If you do not see this, run:

.. code::

   conda info --envs

In the environments list that displays, your current environment
is highlighted with an asterisk (*).

By default, the command prompt is set to show the name of the
active environment. To disable this option::

  conda config --set changeps1 false

To re-enable this option::

  conda config --set changeps1 true


Viewing a list of your environments
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

To see a list of all of your environments, in your Terminal window or an
Anaconda Prompt, run:

.. code::

   conda info --envs

OR

.. code::

   conda env list

A list similar to the following is displayed:

.. code::

   conda environments:
   myenv                 /home/username/miniconda/envs/myenv
   snowflakes            /home/username/miniconda/envs/snowflakes
   bunnies               /home/username/miniconda/envs/bunnies


Viewing a list of the packages in an environment
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

To see a list of all packages installed in a specific environment:

* If the environment is not activated, in your Terminal window or an
  Anaconda Prompt, run:

  .. code-block:: bash

     conda list -n myenv

* If the environment is activated, in your Terminal window or an
  Anaconda Prompt, run:

  .. code-block:: bash

     conda list

To see if a specific package is installed in an environment, in your Terminal window or an
Anaconda Prompt, run:

.. code-block:: bash

   conda list -n myenv scipy


Installing new packages in an environment
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

#. To install a new package in the environment
.. code-block:: bash

    conda install -n myenv scipy  # install the package

#. To install a specific version of a package:

.. code-block:: bash

   conda install -n myenv scipy=0.15.0

TIP: It's best to Install all the programs that you want in this environment
at the same time. Installing 1 program at a time can lead to
dependency conflicts.

.. _pip-in-env:

Using pip in an environment
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

To use pip in your environment, in your Terminal window or an
Anaconda Prompt, run:

.. code-block:: bash

   conda install -n myenv pip
   source activate myenv
   pip <pip_subcommand>


Sharing an environment
^^^^^^^^^^^^^^^^^^^^^^^

You may want to share your environment with someone else---for
example, so they can re-create a test that you have done. To
allow them to quickly reproduce your environment, with all of its
packages and versions, give them a copy of your
``environment.yml file``.

Exporting the environment file
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

NOTE: If you already have an ``environment.yml`` file in your
current directory, it will be overwritten during this task.

#. Activate the environment to export:

   * On Windows, in your Anaconda Prompt, run ``activate myenv``

   * On macOS and Linux, in your Terminal window, run ``source activate myenv``

   NOTE: Replace ``myenv`` with the name of the environment.

#. Export your active environment to a new file::

     conda env export > environment.yml

   NOTE: This file handles both the environment's pip packages
   and conda packages and you can replace the ``environment.yml`` with a path of your choosing.

#. Email or copy the exported ``environment.yml`` file to the
   other person.

.. _create-env-file-manually:

Creating an environment file manually
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

You can create an environment file manually to share with others.

EXAMPLE: A simple environment file:

.. code::

    name: stats
    dependencies:
      - numpy
      - pandas

EXAMPLE: A more complex environment file:

.. code::

   name: stats2
   channels:
     - javascript
   dependencies:
     - python=3.6   # or 2.7
     - bokeh=0.9.2
     - numpy=1.9.*
     - nodejs=0.10.*
     - flask
     - pip:
       - Flask-Testing

You can exclude the default channels by adding ``nodefaults``
to the channels list.

.. code::

   channels:
     - javascript
     - nodefaults


Removing an environment
^^^^^^^^^^^^^^^^^^^^^^^^^

To remove an environment, in your Terminal window or an
Anaconda Prompt, run:

.. code::

   conda remove --name myenv --all

(You may instead use ``conda env remove --name myenv``.)

To verify that the environment was removed, in your Terminal window or an
Anaconda Prompt, run:

.. code::

   conda info --envs

The environments list that displays should not show the removed
environment.

.. _course-env:

Our recommended python installation for this course
-----------------------------------------------------

This installation includes basic python and the IDE spyder

1. Install miniconda
    1. go to https://conda.io/miniconda.html and download the appropriate python 3.6 installer and accept all of the defaults
2. Create a virtual environment for this course (bpes) for basic python for environmental scientists
    1. open anaconda prompt and enter:

.. code-block:: bash

    conda create -n bpes python=3.6 spyder

2. When conda asks you to proceed, type ``y``:

   .. code::

      proceed ([y]/n)?

3. That's it python and spyder for this course should now be installed. To use python with spyder, in the start menu (under anaconda) you should see spyder (bpes).  Open that up and get cracking!

Our recommended python installation for further work
------------------------------------------------------

1. If you have not, install miniconda
    1. go to https://conda.io/miniconda.html and download the appropriate python 3.6 installer and accept all of the defaults
2. Create a virtual environment for your project
    1. select the most applicable .yml files from below and modify it to your needs (change name etc.)
    2. open an anaconda prompt
    3. follow the instructions :ref:`to create an environment from a .yml file <env-yml>`
    4. enter y and press enter when prompted with 'are you sure'
3. That's it python and spyder for your specific project should now be installed. To use python with spyder, in the start menu (under anaconda) you should see a version of spyder followed by your virtual environment's name.  Open that and get cracking!
4. Each time you start a new project go back to 2 and create a new virtual environment.

pre-built python environment files for environmental scientists
----------------------------------------------------------------

We have put together a set of default environments to make the creation of useful environments easier. Below are links
to .yml files, last modified dates, and descriptions of example environments.

# todo set up some defaults for people at ecan and other regional councils -- discuss with mike
# default options (or simply just a chuck option)
# the full monty (everything and it's dog)
# data science and GIS
# data science and statistics
