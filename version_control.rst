Version Control
================

Working in python means that you work flow is all held in a bunch of text files (scripts).  These files are very small
on the drive, but they are worth a huge amount (the sum total of all of your time working on them). In order to protect
these files, most programmers will have some sort of version control. Version control usually consists of an external
backup of the changes to a script through time. This means that if you're computer burns up, you're good you have a copy
of your script. It also means that if you do something terribly stupid you can go back to the previous version of the
script and start again. As an added benefit most modern version control systems allow you to inspect the difference
between versions, helping you keep track of what exactly you have changed.

There are a number of version control systems, but by far the most popular system is git, which is the only system we
will discuss here.


Introduction to GIT
---------------------

Git is a free and open source distributed version control system. Git thinks of its data like a series of snapshots of
a miniature filesystem. With Git, every time you commit, or save the state of your project, Git basically takes a
picture of what all your files look like at that moment and stores a reference to that snapshot. To be efficient,
if files have not changed, Git doesn’t store the file again, just a link to the previous identical file it has already
stored.

Git works locally; a clone (copy) of your project repository is hosted on your computer.  You can commit changes to
these files, which will modify your local project repository. It is then possible to push this repository to a network,
essentially creating a backup of your project repository. In this way you can work offline and simply update your network
hosted repository when you get back to a connection.

Git also has a number of features for collaborating and developing, which basically allow you to develop on a copy of
your repository while leaving the original intact. after you are satisfied with your changes you can merge the two copies.
This uses a feature called branches, which is out of scope for this lesson, but you'll probably come across it while googleing.


Introduction to Github
-----------------------

Github is a cloud hosted
# what is github

# todo how to use github (how to use with spyder???)
https://product.hubspot.com/blog/git-and-github-tutorial-for-beginners
https://guides.github.com/activities/hello-world/
# how much detail do we need to go into for git at the moment?  pull requests?? or just simple commit and push?
# should we outsource this rather than re-creating?... probably not...

Github Classroom
^^^^^^^^^^^^^^^^^^^^^

In this course we use Github Classroom to host the exercises.  Github Classroom allows students to copy repositories to
their own Github account. The new copy is separate from the original repository which allows the student to make changes
without affecting the original.  The author of the repository (the teacher) is also made a collaborater on the project so
they can check in on the student's work and provide feedback.  Our use of Github classroom is fairly simple, we just use
it's copying functionality and will not monitor or provide feedback.
# what is github  classroom

#todo



