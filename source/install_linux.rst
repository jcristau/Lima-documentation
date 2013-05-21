.. _linux:

Linux
=====

Prerequisite
````````````
Before installing Lima on Linux plateform, you need to install the following tools :

	- Python 2.6 or more recent.
	- GCC.
	- Git.

.. _linux_installation:

GetIt
`````
As Lima is not packaged,the only way for now is to retreived it from the git repository.

**Command to get all sources:**

.. code-block:: bash 

  seb@pcbliss01:~/$ git clone --recursive git://github.com/esrf-bliss/Lima.git

**Commands for a minimum chekout to get all source needed for a particular camera:**

.. code-block:: bash

  seb@pcbliss01:~/$ git clone git://github.com/esrf-bliss/Lima.git
  seb@pcbliss01:~/$ cd Lima
  seb@pcbliss01:~/Lima$ git submodule init third-party/Processlib third-party/Sps
  seb@pcbliss01:~/Lima$ git submodule init camera/CAMERA_YOU_WANT_TO_COMPILE
  seb@pcbliss01:~/Lima$ git submodule update

Particular version
``````````````````
On all version of LImA is tagged. So you can retreive a particular version.

This command provide the tag list:

.. code-block:: bash

  seb@pcbliss01:~/Lima$ git tag -l
  core-1.0.10
  core-1.0.11
  core-1.0.12
  core-1.0.13
  core-1.0.9
  espia-1.0.4
  espia-1.0.5
  ....
  taco-camera-frelon-1.0.5
  tango-camera-frelon-1.0.0
  tango-camera-maxipix-1.0.2
  tango-camera-maxipix-1.0.4
  tango-camera-pilatus-1.0.2
  tango-common-1.0.2
  tango-common-1.0.3
  tango-common-1.0.4
  tango-common-1.0.5
  tango-common-1.0.6

Let's say that you want the version 1.0.11 of Lima core with this command, you'll getit:

.. code-block:: bash

  seb@pcbliss01:~/Lima$ git checkout core-1.0.11
  seb@pcbliss01:~/Lima$ git submodule init
  seb@pcbliss01:~/Lima$ git submodule update

.. _git: http://git-scm.com/

.. _linux_compilation:

Compilation
```````````
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

* Configure all module and stuff (don't need if you just want C++ libraries)

.. code-block:: sh

  make config

* Finally compile all C++ libraries

.. code-block:: sh

  make

* If you need Python modules

.. code-block:: sh

  make -C sip -j3

**That's all folks ;)**
  
Installation
````````````
Installation on Linux is pretty easy because it's manage by Makefile.
But those Makefile can only be used if you have compile everything including Python modules. Otherwise It'll failed.
See :ref:`linux_compilation`

.. code-block:: sh

  make install

you can specify the destination path with this variable **INSTALL_DIR**

By the way, this command only install C++ libraries and Python module, :ref:`tango_installation` is an other step.

