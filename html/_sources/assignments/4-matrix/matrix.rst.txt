.. highlight:: java

Matrix Assignment
=================

Matrices have many
different uses and applications both in math and science. In fact, many of you
will use matrices in physics in order to solve systems of
equations.

As with the last assignment, there is a list of methods that for your class to include. In
addition, you should work to create some of your own test classes in order to
test your matrices.

This assignment can seem very daunting at first. Before you decide what
instructions you want to give your computer, you have to determine how you
would manipulate a matrix first. So, we recommend that you start by trying to
modify a few different matrices into the identity matrix.

`Link to the Matrix JavaDoc
<https://kjergens.github.io/csxdocs-build/_static/matrix-javadoc/main/Matrix.html>`_

.. note::
    except for ``setEntry()``, none of the functions 
    should actually modify the original ``Matrix``. Instead, the functions
    return an entirely new ``Matrix``. Make sure, when you are filling out
    these functions, that you are not modifying the original ``Matrix``, but
    rather the ``Matrix`` that you will return.

It will be very important to identify your edge cases when you are testing.
Again, much of the work of this project will be to refine your algorithm once
you think you know what the basic logic should be. How will you handle
non-square matrices? Uninvertible matrices?

Additionally, think about how you can tell your program is working correctly.
It's hard to look at an inversion of a matrix and tell if it's correct, so try
to use the properties of inverse matrices in order to make testing easier.
Also remember that it is very hard to naturally come by a singular (i.e.
uninvertable) matrix by chance, so you might want to intentionally create
singular matrices.


Matrix Assignment
-----------------

Remember to **document as you go.** Each method you write should
have a documentation comment (ideally in the JavaDoc format)
before it::

    /**
     * [DESCRIPTION OF WHAT THE METHOD DOES]
     *
     * @param left [DESCRIPTION OF THE 'left' PARAMETER]
     * @param right [DESCRIPTION OF THE 'right' PARAMETER]
     * @param subintervals [DESCRIPION OF THE 'subintervals' PARAMETER]
     * @return [DESCRIPTION OF WHAT THE METHOD RETURNS]
     */
    public double calculateDeltaX(double left, double right, int subintervals) {
        // the actual method
    }

Base Assignment
----------------  

1. Matrix Class
^^^^^^^^^^^^^^^^^^^  
.. admonition:: Exercise

  **Summary**: Create a Matrix object that performs common matrix operations.

  #. Create a package namespace called ``matrix``.
  #. In ``matrix`` create a class called ``Matrix``.
  #. Add a ``private`` attribute called ``matrix`` that is a two-dimensional array of ``double`` s.
  #. Write the Matrix constructor, which sets the size of the ``matrix``. 
  #. Implement the rest of the methods in the `Matrix JavaDoc <https://kjergens.github.io/csxdocs-build/_static/matrix-javadoc/main/Matrix.html>`_
  #. Optionally, create other constructors to help you fill your matrix.

2. Test Classes
^^^^^^^^^^^^^^^^^
.. admonition:: Exercise

  **Summary**: Test the Matrix methods.

  #. In the ``test`` folder, create a class called ``MatrixTest`` and import all the necessary JUnit libraries.
  #. In the class, but outside of any methods, create a global Matrix variable of some size, e.g. ``Matrix matrix = new Matrix(10, 10);``
  #. Write several test methods to every method in the ``matrix`` object.

Extension
------------

There are several parts of the Extension that are highly suggested (and are
covered in the Latex book that Dr. Gomprecht presented). In addition, there
are some extensions that previous students have completed, although they are
more ambitious.

1. Use your ``Matrix`` class in order to differentiate polynomials using the
   VDM. While this is technically an extension, as long as you are able to
   get your ``Matrix`` class to work, you should hopefully be able to complete
   this.
2. Use your ``Matrix`` class to interpolate polynomials (more below).

   a. Interpolate the equation of accumulation functions. Note: is there a
   pattern that you notice when you differentiate an accumulation function or
   when you accumulate a function's derivative?

You could also make a GUI. Even if you choose not to make a GUI, you should
definitely have a way in which people can input their own polynomials through
a command line interface.

Polynomial Interpolation
^^^^^^^^^^^^^^^^^^^^^^^^^

Some of you actually conducted polynomial interpolation with Simpson's Rule
for the Riemann assignment extension. 
