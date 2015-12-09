.. _linux:

Linux
=====

Prerequisite
````````````
Before installing Lima on Linux platform, you need to install the following packages:

        - cmake
	- Python 2.6 or more recent
	- GCC
	- Git
	- Gnu Scientific Library, libgsl is available within most of the linux flavour
	- sip tool (version >=4.2), used for generating the python binding

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
All versions of LImA are tagged. So you can retreive a particular version.

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

Let's say that you want the version 1.0.11 of Lima core with this command, you'll get it:

.. code-block:: bash

  seb@pcbliss01:~/Lima$ git checkout core-1.0.11
  seb@pcbliss01:~/Lima$ git submodule init
  seb@pcbliss01:~/Lima$ git submodule update

.. _git: http://git-scm.com/

.. _linux_compilation:

Compilation
```````````
The build is managed by the toplevel CMakeLists.txt.

* First make a build directory, cd to it and run the cmake config tool:

.. code-block:: sh

  mkdir build && cd build && ccmake ..

* Configure the modules you want to build

* Finally compile all C++ libraries (and python modules, if selected)

.. code-block:: sh

  make

**That's all folks ;)**

.. _linux_installation:

Installation
````````````
Installation on Linux is pretty easy because it's managed by cmake.

.. code-block:: sh

  make install

you can specify the destination path with the **CMAKE_INSTALL_PREFIX** variable in ccmake or at the cmake invocation.

With your new installation you may need to update your environment for both python and library paths:

.. code-block:: sh

  export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:<my-new-install-dir>/lib

  export PYTHONPATH=$PYTHONPATH:<my-new-install-dir>/lib/pythonX.Y/site-packages



**WARNING**: *"make install"* only installs C++ libs and python modules, the application like the python Tango server (LimaCCDs) code remains under applications/tango. Please go to :ref:`tango_installation` for further instructions.

