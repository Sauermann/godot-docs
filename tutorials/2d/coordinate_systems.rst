.. _doc_coordinate_systems:

Coordinate Systems
==================

This tutorial gives an in-deepth look at the different coordinate systems, that you
might come across in the course of interaction with Godot.

As a convention, in godot 2D-coordinates (x, y), the first number x of the pair denotes
the horizontal axis and the second number y denotes the vertical y axis.
Numers increase to the right and downwards.

.. _coordinate_systems_screen:

Screen coordinates
------------------

The monitor on which you are looking at this documentation right now, has a certain
resolution. For Full HD, it is 1920x1080 pixel. These are called screen coordinates.

The coordinate (0, 0) corresponds to the pixel at the top left position of the monitor.
On a Full HD monitor, the pixel at the lower right corner has the coordinate (1919, 1089).

Window coordinates
------------------

Graphical operating systens display the content of programs in windows, for example
the Godot editor window or the window of a game.

The :ref:`Window <class_Window>` class provides access to the coordinates of the window
with the two properties :ref:`position<class_Window_property_position>` and
:ref:`size<class_Window_property_size>`. Since they include windowborders, they provide no
reliable way for content positioning.




The way of a Mouse Click
========================

Lets follow a mouse click event through the transformations it takes on the way to it's
final target.

Screen
------

The Mouse Click happens at the screen coordinate ``(400, 400)``


Window
------

The Window is placed at the coordinates ``(190, 90)`` with a size of ``(620, 620)``,
including a border width ``10`` pixel at each side. The means that the viewport of the window
is located 

The click happens within the space of the window and the OS sends the Mouse Click event to
Godot. The coordinates sent within this event are adjusted to the window position and to the
window border. This means, that the event contains the coordinate
``(200, 300) [= (400, 400) - (190, 90) - (10, 10)]``

The first time, you can come into contact with the event in the root
:ref:`Window <class_Window>` Node, the position is aready adjusted, so you don't need to
worry about window borders or position.




Ende
