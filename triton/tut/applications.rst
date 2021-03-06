============
Applications
============

.. admonition:: Video

   `Watch this in the Winter Kickstart 2021 course <https://www.youtube.com/watch?v=_YMO-1dPc1E&list=PLZLVmS9rf3nN_tMPgqoUQac9bTjZw8JYc&index=8>`__

In this tutorial, we talk about the overall process of finding,
building, and compiling software.  These days, installing and managing
scientific software is taking more and more time, thus we need to
specifically talk about it some.

.. seealso::

   Main article: :doc:`../apps/index`

.. admonition:: Local differences

   Almost every site will use modules.  The exact module names, and
   anything beyond that, will be different.  Containers are becoming
   more common, but they are less standardized.

Available softwares
===================

You can find what softwares we have available in different ways:

* First, you should check our :doc:`Applications  <../apps/index>` page
  and see if the software you need is already available and has
  instructions.
* If you find the software you need available, you can usually load it via a module.
  The next tutorial, :doc:`Software modules <modules>` explains what modules
  are and how to work with them.
* You can also search this tutorial to see what you can find (though
  note that not everything is in the Triton section here - some applies
  to Aalto workstations or own computers).
* It's always a good idea to search the `issue tracker
  <https://version.aalto.fi/gitlab/AaltoScienceIT/triton>`__ to see if
  there are previous issues about it - not everything is always
  updated.



Modules
=======

You can learn about modules on the :doc:`Software modules <modules>` tutorial.
But generally, ``module`` is a command that allows you to get and remove
access to other software - because not everything can be available at once.
The :doc:`Software modules <modules>` tutorial teaches how to
load modules using the command ``module load $NAME``, etc.

Not all of the software we have available is documented.  You can
``module spider $NAME`` to try to see if you can find a module
that way.  Note that this is *partially* case sensitive so it can
be hard to find things - you might need to look through ``module
avail`` too, to find all the available modules.


Common applications
^^^^^^^^^^^^^^^^^^^

.. important::

   This is Aalto-specific.  Some of these will work if you ``module
   load fgci-common`` at other Finnish sites (but not CSC).  This is
   introduced in the next lesson.

For reference, here is the most common software:

.. include:: ../ref/software.rst

If one of these ``module load`` commands does not work at your site,
try ``module spider $NAME`` and see if you can find it.  This is
actually covered under the upcoming :doc:`modules <modules>` tutorial.

Singularity containers
======================

.. seealso::

   Main article: :doc:`../usage/singularity`

Some softwares have become so complicated that they just can't be installed,
and for that we use containers.  A software container is basically a
complete self-contained operating system environment.  Another
advantage of containers is that they make it easy to move installed
software from system to system, so that you can have the same
environment everywhere.

You can read about singularity containers :doc:`here <../usage/singularity>`.
If you load a module that uses singularity, nothing will happen at first.
You execute your software using ``singularity_wrapper exec``,
or use ``singularity_wrapper shell`` to get a shell in there.

We also provide :doc:`some containers built by NVIDIA <../apps/nvidiacontainers>`.
These containers are from NVIDIA's NGC-repository and meant for GPU
computations.

Requesting new software
=======================

We aim to install a good base of software for our users - but it's not
possible to keep up with all requests.  If you need something, submit
a request to our :ref:`issue tracker <issuetracker>`, but be aware
that despite best efforts, we can't do everything.
See the main :doc:`Applications <../apps/index>` page for more information.


A plea: make your software reusable!
====================================

Five years from now, when you are releasing your own software that you
want others to use, :doc:`make it easy to install and reusable
</scicomp/packaging-software>`.


Exercises
=========

If you are at Aalto, everything will work.  Otherwise, if you are in
Finland (but not at CSC) ``module load fgci-common`` will make our
modules available on your cluster.

1. Figure out how to use ``tensorflow`` (this is not a software
   problem, but a searching the documentation problem).  Make it work
   enough to do ``python`` and ``import tensorflow`` -- though you
   will get an error which you will learn to solve in a later lesson.

2. Figure out how to load the module for NVIDIA's tensorflow container.
   Using ``singularity_wrapper``, run ``python -V`` and obtain python version.
   Compare that to the python version on the login node.
   Try ``singularity_wrapper shell`` too and use ``cat`` to check the
   operating system version stored in ``/etc/issue``: ``cat
   /etc/issue``.  Verify that this is different from what is outside
   the container.

3. Find the Applications page link above, and check the list for ways
   to find out if we already have your software installed.  See if we have
   what you need, using any of the strategies on that list.

4. (optional) From the Applications page, find the Spack package list
   (warning: it's a very long page and takes a while to load).  Does
   it have anything useful to you?

5. (optional) Discuss among your group what software you need, if it's
   available, and how you might get it.



What's next?
============

The next tutorial covers :doc:`software modules <modules>` in more detail.
