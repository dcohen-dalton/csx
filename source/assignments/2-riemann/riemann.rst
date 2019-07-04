Riemann Sum Assignment
======================

.. figure:: fig1.svg
   :width: 25 %
   :align: center

Approximating Area Under a Curve
--------------------------------

.. Gomp's original text:
.. A Riemann sum is, in almost all cases, only an approximation to the area
.. under a curve. We’ve seen this in math class. We’ve also seen that as the
.. width of the rectangles in a Riemann sum gets smaller the approximation
.. to the area under the curve improves. In some cases, we’ve been able to
.. use this fact to compute the exact value of the area under the curve. In
.. many cases, though, the sum is too complicated to be computed by hand.
.. This is where computers can be of help. For this project you’ll create a
.. Riemann class which evaluates a given Riemann sum.

The focus of this assignment will be defining and calculating
the area under a curve. The following slides, created by Dr. Gomprecht,
contain an introduction to the concept of **Riemann sums**, which
provide a way of approximating this area:

:download:`Area Under a Curve Slides </_static/RiemannSumSlides.pdf>`

We have seen that as the width of the rectangles in a Riemann sum gets smaller
the approximation to the area under the curve improves. In some cases, we’ve
been able to use this fact to compute the exact value of the area under the
curve. In many cases, though, the sum is too complicated to be computed by
hand.

This is where computers can be of help. Calculating a Riemann sum requires
adding up many small areas to get an approximation of the total area under the
curve. Computers are good at this kind of repetitive task: while there are many
steps, the calculation involved in each step is simple. In Compsci 1 and 2,
you learned how to tell a computer to do the same thing over and over using
``for`` and ``while``-loops. Now, you will apply this knowledge to create a
Java class which evaluates a given Riemann sum.

.. figure:: fig2.svg
   :width: 80 %
   :align: center

   The individual rectangles' areas can be added up using a ``for``-loop.
   The more iterations (steps) of the loop, the better the approximation.

.. admonition:: Exercise

   The syntax of ``for``-loops in Java can be hard to remember.

   * Use a ``for``-loop to print the first 100 positive integers.
   * Use a ``for``-loop to add up the first 100 positive integers.
   * Use a ``for``-loop and an array to find the mean of the following ten numbers:
     ``28.2, 14.7, 10.3, -2.0, 55.8, 10.3, 0.2, 1.0, 0.0, 25.1``

The Riemann Class
-----------------

In order to calculate Riemann sums you will need to write more than one class. This is because of the different rules that are used. Regardless of the rule, calculating a Riemann sum inevitably involves adding together the area of all of the individual slices. So, that leaves a few options for how to structure this project. For this assignment, you will write an **abstract class** which several child classes, each corresponding to a different rule, extend. Using class inheritance in order to structure this project enables you to avoid writing redundant code. 

Abstract Classes and Methods
^^^^^^^^^^^^^^^^^^^^^^^^^^^^
An abstract class is never instantiated, which is why it's called "abstract." This type of class is used in situations where you want several associated classes to share certain methods.

Abstract methods are declared similarly to normal methods. However, they do not have a method body (the part of a method that is contained in curly braces).

You will be given the Javadoc for an abstract class below. Using this documentation, you should fill in the methods as specified in order to meet the requirements.

**LINK TO DOCUMENTATION**

In each child class of **Riemann** you will write a different **slice** and **slicePlot** method. 

The Assignment
--------------

The base assignment: 

#. Write the **Riemann** abstract class based on the provided documentation.
#. Write classes for Right Hand Rule, Left Hand Rule, and Trapezoid Rule which extend **Riemann**.
#. Use your program to answer the following question: which of the three rules above is the most accurate?

For your extension, research different Riemann sum rules and write classes for them in the same style as the base assignment. Below are some suggested extensions that students have done in the past:

* Maximum Rule
* Minimum Rule
* Random Rule
* Midpoint Rule
* **Simpson's Rule** - this requires far more work than the other options but is also the most interesting. It will take some outside research.

There is also the option to create a User Interface that makes it easier to run your program. Even if you decide not to dedicate a lot of time to making an interface, you should at least have some way for a user to run your program with desired parameters without having to directly edit the code first.