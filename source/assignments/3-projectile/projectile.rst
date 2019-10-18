Projectile Assignment
=====================

Introduction to Simulations
---------------------------

.. figure:: test3.gif
  :width: 100%
  :align: center

This assignment will focus on projectile motion. You have already learned how
to track the movement of a massless particle using kinematics equations.
However, there are some limits to what you are able to calculate by hand.
Therefore, it can be useful to instead use a computer model to simulate the
movement of a particle.

There are certain assumptions that are made in the kinematics equations you
use in your physics classes. You treat the projectiles that you use in
problems as massless points. These assumptions allow you to solve problems
more easily and provide close approximations to the "correct" answer. You will
also need to make some assumptions in the simulations you build.

You should construct your simulation in layers of complexity, which means that
the first draft of your simulation should be as simple as possible. Then, you
can start to add on features and tweak your code to get closer and closer to a
more accurate model. Alternatively, trying to make your simulation too
complicated too quickly will likely give you issues when you try to debug.

For this assignment, Mr. Condie will come into class and give a lecture about
how you should structure your code which will serve as an overview of the
assignment. It is very important that you take notes, as this lecture will be
the foundation of your work throughout this project.

Coding Models
-------------

You will use ``AbstractSimulation`` for every physics project in this class.
As the name implies, it is an abstract class with some abstract methods, just
like you learned about in ``Riemann``.

Getting Started with ``AbstractSimulation``
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

#. Open the window to create a new class in your package.

   - Name the class [...]App. This is the naming convention for your
     simulation classes.
   - Before you click **Finish**, click the **Browse** button
     next to the **Superclass** text box. Choose ``AbstractSimulation`` and
     click **OK**.
   - Under the "method stubs" section, choose to click the box next to ``public
     static void main(String[] args)``.
#. Declare the following two functions:

   - ``public void initialize()``
   - ``public void reset()``

#. In ``main()``, add this line: ``SimulationControl.createApp(new
   nameOfClass());``

.. note::
    It might be useful to look at the **JavaDoc** for ``AbstractSimulation``
    in order to see for yourself what its methods look like. In the future, if
    you ever want to learn more aout a class, checking the documentation is a
    good place to start.

Control Panel
^^^^^^^^^^^^^^^^

.. figure:: control-panel.svg
  :width: 50 %
  :align: center

Your simulation app will automatically generate a pop-up window called a
**Control Panel**. The **Control Panel** makes incorporating a lot of user
input easy. Notice that there are three buttons on the **Control Panel**.
**Initialize** and **Reset** each correlate to the ``initialize()`` and
``reset()`` functions, respsectively. So, pressing the **Initialize** button
on the **Control Panel** will run ``initialize()``. The **Step** button will
run the code in your ``doStep()`` exactly once.

``doStep()``
^^^^^^^^^^^^^^^

``doStep()`` is a function that is repeatedly called while the simulation is
running. You can think of it as a looping ``main()`` function, or as a
built-in while loop that always has a true condition. Since the code
in ``doStep()`` will be repeated thousands of times throughout the course of
the simulation, it is very important to think about how you will optimize your
code so that it is as computationally efficient as possible.

.. note::
  You can make your simulation a little faster by avoiding updating your
  graphics every ``doStep()``. Instead of just telling the simulation app to
  run the ``doStep`` less often, which will just slow the simulation down, or
  increasing your time interval, which will make your calculations less
  accurate, you can put a ``for`` loop inside of your ``doStep()``. If you run
  calculations inside of the ``for`` loop and update your grpahics outside of
  the loop, you can determine for yourself how many times you want to allow
  the calculations to update before the graphics update.


``initialize()``
^^^^^^^^^^^^^^^^^

``initialize()`` runs directly after ``reset()`` and right before the first
``doStep()``. As the name of the function suggests, it is a good time to get
everything set up for your simulation. During this step, you should take all
of the input from the **Control Panel** and store it in variables in your
code. You can do this by running ``control.getDouble()``,
``control.getString()``, etc., using the appropriate function for your desired
data type.

``reset()``
^^^^^^^^^^^^

``reset()`` runs once every time you run your simulation app. You should add
all of the information to the **Control Panel** that you want the user to be
able to update with their own input. You can do this by writing
``control.addValue("variableName", variableValue)``. Additionally, if you stop
a simulation that is already initialized and running, you can press the
**Reset** button to restart it and reinitialize it. In order to use this
feature, during ``reset()`` it is best to clear off all of your graphics.

.. admonition:: Exercise

    Even though you've now read about AbstractSimulation, it is useful to get
    some practice before you jump into the assignment. Try to make a
    simulation that moves a circle upwards on the screen.

Assignment
----------

You will have to use the AbstractSimulation class for this project. Your
simulation class should **extend** AbstractSimulation. You will also need to
construct a **Particle** class. Try to be as thorough and thoughtful as
possible when you make this class, because you will likely use it in the rest
of your physics assignments.

When you make the **Particle** class, consider what variables might affect how
a projectile moves in air. These variables should be the **fields** in the
class.

.. note::
  While it can be tempting to code everything at once and then test it all at
  the end, the graphics are actually often helpful in order to give you a
  sense of what's working and what's not.


Base
^^^^^

There are two parts of the base assignment. Part III will take much longer than
Parts I and II; it is essentially a mini-extension. (In fact, one year it was
someone's extension.) While everyone in the class will do the same base
assignments, you will not necessarily all get exactly the same values. This
will depend on how you choose to calculate your position variables, your
timestep, and, for Green Monster (Part III), the way that you run your
different iterations.

Since there is no "right" answer, it can be difficult to tell if you are on
the right path. You can try to compare answers with your fellow students to
see if your approximations are at least close to each other. You can also try
to calculate some of these scenarios by hand in order to see whether you get
an answer that's close. However, in the end, the goal is not really to get a
certain "right" answer (since everything we do is an approximation), but
rather to get an understanding of the physics concepts and their
implementation.

Before you start your base assignments, consider:

- What variables might affect the flight of your particle? These variables
  should be your fields.
- What variables should the user be able to input?
- How will you represent your particle on the screen?

Part I
^^^^^^^

The first part of the assignment is just to simulate a one dimensional
particle that is only subject to gravity and air resistance. You learned
different ways to calculate air resistance in class. There are three different
equations for air resistance that you learned:

#. Assume that air resistance is zero.
#. Air resistance is directly proportional to velocity.
#. Air resistance is directly proportional to velocity squared.

You will make three particles that move in one dimension. Each particle will
use one of the three methods of calculating air resistance.

In addition to showing each particle moving on screen, you should also plot
position, velocity, and acceleration. Before you plot these values, try to
think about what graphs might make sense. What should the acceleration of a
particle without air resistance look like? What should the acceleration of a
particle with air resisance look like?

.. note::
  Make sure that your air resistance is affecting the particle in the right
  way (i.e., check the direction of the air resistance as the particle moves.
  Which way should the air resistance vector be pointing in relation to the
  particle's velocity?)

Part II
^^^^^^^^^

The second part of the assignment is to simulate the projectile experiment you
are conducting in your physics classes. You will need to modify the simulation
you made for Part I in order to show a projectile moving in two dimensions.
Think about what you learned in physics class about the golden rule in order
to add this second dimension.

Once you have your two dimensional particle working, find the value for
**beta** that accounts for your experimental error.


Part III
^^^^^^^^^^

The Green Monster is a wall in Fenway park. It is 10 meters tall and 100
meters away from home plate. Your assignment is to find the angle at the
minimum velocity necessary to hit a particle from 1 meter off of the ground
at home plate over the wall.

Extension
-----------

Your task for your extension is to model an object that moves in two
dimensions.

Physics extensions are very open ended, and the above prompt is not very
exact. You should work through your idea for your extension in lab with Mr.
Condie in order to determine together what might be a realistic goal based on
your initial idea. While you work on the base assignment, you should think
about what you might be interested in modeling.

The most important component of this extension is your understanding of the
underlying physics concepts. While looking up equations onlilne might give you
a realistic simulation, you will not learn anything if you don't understand
why the formulas that you use will give you good approximations.

Once you know what you want your extension to be, just as you did in
``Riemann``, you will build off of the code you already wrote for your base
assignment. You will present the extension to the class and the teachers, so
be ready to talk about what you learned and to answer some questions.

.. TODO: Add something about past extensions?

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

`Displaying Simulations using OSP <https://kjergens.github.io/csxdocs-build/display-osp/display-osp.html>`__
