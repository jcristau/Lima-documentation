.. Lima documentation master file, created by
   sphinx-quickstart on Fri Feb 18 10:19:02 2011.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

====================================
LIMA : Library for Image Acquisition
====================================
Lima ( **L** ibrary for **Im** age **A** cquisition) is a project for the unified control of 2D detectors. The aim is to clearly separate hardware specific code from common software configuration and features, like setting standard acquisition parameters (exposure time, external trigger), file saving and image processing.

A PDF version of this documentation is available: `pdf documentation`_

Overview
--------

.. toctree::
  :maxdepth: 2

  overview
  
LImA specification
------------------

The first LIMA project specification has been written after the previous brain storming sessions. It is composed by the following main topic

.. toctree::
  :maxdepth: 1

  lima_specification_overview
  lima_specification_control
  lima_specification_hardware

.. _compilation:

.. _installation:

Installation
------------

.. toctree::
  :maxdepth: 3


  install_windows
  install_linux
  install_tango_device_server

Supported Cameras
-----------------

.. toctree::
  :maxdepth: 2

  supported_cameras

Future cameras
--------------

.. toctree::
   :maxdepth: 2

   future_cameras

Applications
------------

.. toctree::
  :maxdepth: 3

  applications/tango/doc/index

Camera plugin developer guide
-----------------------------

.. toctree::
  :maxdepth: 3

  plugin_getting_started/index

`Class documentation`_
----------------------

Indices and tables
------------------

* :ref:`genindex`
* :ref:`modindex`
* :ref:`search`

.. _Class documentation: doxygen/html/index.html

.. _pdf documentation: ../latex/Lima.pdf

