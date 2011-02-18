.. _compilation:

Compilation
===========

.. _linux_compilation:

Linux
`````

Every think is managed by root Makefile. 

* So first generate the config.inc file.

.. code-block:: sh

  make

* Edit the configuration file **config.inc** 

.. code-block:: sh

  COMPILE_CORE=1
  COMPILE_SIMULATOR=1
  COMPILE_SPS_IMAGE=1
  COMPILE_ESPIA=0
  COMPILE_FRELON=0
  COMPILE_MAXIPIX=0
  COMPILE_PILATUS=0
  COMPILE_CBF_SAVING=0
  export COMPILE_CORE COMPILE_SPS_IMAGE COMPILE_SIMULATOR \
         COMPILE_ESPIA COMPILE_FRELON COMPILE_MAXIPIX COMPILE_PILATUS \
         COMPILE_CBF_SAVING

* Configure all module and stuff

.. code-block:: sh

  make config

* Finally compile all C++ libraries

.. code-block:: sh

  make

* If you need Python modules

.. code-block:: sh

  make -C sip -j3

**That's all folks ;)**