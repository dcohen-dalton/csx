.. highlight:: java

Matrix Assignment
=================

By now, you've heard Dr. Gomprecht's lecture on matrices, which can be found
here. Matrices, as he told you, have many different uses and
applications both in math and science. In fact, many of you will use matrices
in physics later in the year in order to solve systems of equations.

As with the last assignment, Dr. Gomprecht has already scaffolded some of the
code for you. He has a list of methods that he wants your class to include. In
addition, you should work to create some of your own test classes in order to
test your matrices.

This assignment can seem very daunting at first. Before you decide what
instructions you want to give your computer, you have to determine how you
would manipulate a matrix first. So, we recommend that you start by trying to
modify a few different matrices into the identity matrix.

`Link to the documentation
<../../_static/matrix-javadoc/main/Matrix.html>`_

.. note::
    None of the functions, either than ``getEntry()`` and ``setEntry()``,
    should actually modify the original ``Matrix``. Instead, the functions
    return an entirely new ``Matrix``.

It will be very important to identify your edge cases when you are testing.
Again, much of the work of this project will be to refine your algorithm once
you think you know what the basic logic should be. How will you handle
non-square matrices? Uninvertible matrices?

.. math::
    \begin{bmatrix}
    3 & 2 & -1 \\
    0 & -7 & 4 \\
    -1 & 6 & 2 \\
    \end{bmatrix}

Matrix Assignment
-----------------
