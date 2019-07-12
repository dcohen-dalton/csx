Projectile Assignment
=====================

.. figure:: fig1.svg
   :width: 25 %
   :align: center

Introduction to Modeling
------------------------
.. from blogs.dalton.org

Modeling is a concept that has broad definitions and meanings, even in
science. We may never know the ‘true’ nature of the Universe and the laws
governing its evolution – however, as scientists, we have made giant strides
in discovering ever more precise approximations of its nature. These models
enable us to understand how its different elements and systems interact. We
can sometimes make predictions of future events or understand why that is
impossible. Newton’s Laws of Motion, General Relativity, Quantum Mechanics,
and String Theory are but a few of the fundamental models of different realms
of the universe around us.

Another way that science uses the idea of a model is when working within one
of the models above. We simplify situations, hoping to include only the
dominant physics that will model most of what we observe. For example, when
understanding the orbit of the earth around the sun, we might start with these
simplifications:

- The earth is the only planet
- The earth doesn’t have a moon
- The sun is fixed in space

Using this model allows us to understand much, but not all, of the dynamics of
a solar system.

Since many models in Physics are described mathematically, the simplified
models scientists work with involve solving mathematical systems of varying
complexity. Sometimes these systems can be solved ‘by hand’ with the tools you
are currently acquiring. More often the systems are too complex and their
solutions must be found in another way. One way to do this is with a computer
simulation – another tool you are learning to employ.

Modeling Projectile Motion
--------------------------

You are standing on the Brooklyn Bridge holding a rock. If you throw the rock
and watch it fly through the air, what quantities can you determine?

- If you know the rock’s initial velocity, and can determine where it lands,
  what can you learn about the height of the bridge?
- If you already knew the height, could you predict where it would hit the
  water?

You will begin to model the answers to these questions by creating a computer
simulation of the rock’s motion.

A Simulated Particle
^^^^^^^^^^^^^^^^^^^^

You will begin by creating a ``Particle1D`` class to model the motion of a
particle---in this case, a rock---in one dimension. Just like the real rock,
we want our simulated rock to have certain properties at a given time. These
properties correspond to the **fields** (member variables) of the
``Particle1D`` object.

- What properties does a real particle have?
- What fields should an object of this type have?

You should add a constructor to ``Particle1D`` which takes initial values
for these properties and initializes the particle accordingly.

Moving the Particle
^^^^^^^^^^^^^^^^^^^

Now that the ``Particle1D`` class has fields which describe its properties,
it's time to add a method, ``step()`` which handles its motion. While
particles move continuously in real life, you will model them as moving in
discrete steps. In each step, a certain amount of time (:math:`\Delta t`)
should pass and the particle's properties should be updated. You
may structure this method how you see fit, but it must:

- Take a parameter, :math:`\Delta t`, and pass that amount of time.
- Use motion equations you have learned in physics class to update
  the properties of the particle. The question you should be asking yourself
  is **"if** :math:`\Delta t` **seconds pass, what are the new properties of
  the particle?"**

.. admonition:: Pseudocode

   When creating an algorithm, it can be helpful to start by writing
   **pseudocode**: text which describes a program without having to
   follow exact Java syntax. For example, the pseudocode for a program
   which finds the largest number in an array could be:

   .. code-block:: text

      set LARGEST to the first element in the array

      for each element in the array:
        if CURRENT_ELEMENT is greater than LARGEST:
          then set LARGEST to CURRENT_ELEMENT
        otherwise do nothing

      output LARGEST

   As you write pseudocode, imagine that a human will be reading and running
   your program, rather then the computer.

Setting up a Simulation
-----------------------

`<../../display-osp/display-osp.html>`__
