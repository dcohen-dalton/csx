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
