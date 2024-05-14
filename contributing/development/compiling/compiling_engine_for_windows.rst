.. _doc_compiling_engine_for_windows:

Compiling Engine for Windows
============================

.. highlight:: shell

Requirements
------------

For compiling under Windows, the following is required:

- `Visual Studio Community <https://www.visualstudio.com/vs/community/>`_. VS 2022 
  is recommended.
- `ONNXRUNTIME <https://github.com/microsoft/onnxruntime>`_. v1.17.1 is recommended.
  You can download directly from the `onnxruntime-win-x64-1.17.1.zip <https://github.com/microsoft/onnxruntime/releases/download/v1.17.1/onnxruntime-win-x64-1.17.1.zip>`_ 
  or `onnxruntime-win-x64-cuda12-1.17.1.zip <https://github.com/microsoft/onnxruntime/releases/download/v1.17.1/onnxruntime-win-x64-cuda12-1.17.1.zip>`_ or 
  `onnxruntime-win-x64-gpu-1.17.1.zip <https://github.com/microsoft/onnxruntime/releases/download/v1.17.1/onnxruntime-win-x64-gpu-1.17.1.zip>`_.
- `pybind11 <https://github.com/pybind/pybind11>`_.
- `CMake 3.5+ <https://cmake.org/download/>`_ build system.
- `Python3 <https://www.python.org/downloads/>`_.
- `Miniconda <https://cmake.org/download/>`_ for creating Python2 environment.
- `Python2 <https://cmake.org/download/>`_ for running cuckoo sandbox. You will need also `Microsoft Visual C++ Compiler for Python 2.7 <https://web.archive.org/web/20190720195601/https://download.microsoft.com/download/7/9/6/796EF2E4-801B-4FC4-AB28-B59FBF6D907B/VCForPython27.msi>`_.

.. seealso:: To get the Scorpion source code for compiling, see
             :ref:`doc_getting_source`.

..             For a general overview of CMake usage for Scorpion, see
..             :ref:`doc_sam_buildsystem`.

             Check :ref:`doc_compiling_console_for_windows` for compiling 
             the console.

Setting up CMake
----------------

To install CMake, download the installer from the `CMake website <https://cmake.org/download/>`_ and run it.

You can then check that CMake is installed by running ``cmake --version`` in a command prompt.

.. _doc_compiling_engine_for_windows_install_vs:

Downloading Scorpion's source
-----------------------------

Refer to :ref:`doc_getting_source` for detailed instructions.

.. warning::

    To prevent slowdowns caused by continuous virus scanning during compilation,
    add the Scorpion source folder to the list of exceptions in your antivirus
    software.

    For Windows Defender, hit the :kbd:`Windows` key, type
    "Windows Defender Settings" then hit :kbd:`Enter`.
    Under **Virus & threat protection**, go to **Virus & threat protection setting**
    and scroll down to **Exclusions**. Click **Add or remove exclusions** then
    add the Scorpion source folder.

Running CMake
~~~~~~~~~~~~~

.. code-block:: shell

    mkdir .build && cd .build
    cmake .. -G "Visual Studio 17 2022" -DSAM_STATIC_ANN_ONNX_MODELPATH="path/to/ANN-78M-in2381-h11-out1-v0.onnx" 
                                        -DSAM_STATIC_ANN_STANDARDIZE_PARAMS="path/to/standardize-params-20240307_181717.pkl" 
                                        -DSAM_STATIC_CNN_COLORMAP="path/to/gray_colormap.npy" 
                                        -DSAM_ONNXRUNTIME_ROOTDIR="path/to/onnxruntime-win-x64-1.17.1/" 
                                        -DSAM_STATIC_CNN_ONNX_MODELPATH="path/to/CNN-model3-167M-in(1,256,256)-out1.onnx" 

.. note:: You need to download our trained models in order to compile the engine. 
          Check :ref:`doc_models` for more information.

You can build then with:

.. code-block:: shell

    cmake --build . --config Debug

.. note:: When compiling with ``-DSAM_BUILD_TESTS=ON``, you will get multiple 
          warnings about linking, you can ignore them.

If all goes well, you will have our engine's ``.lib`` and ``.dll`` files in the ``.build`` folder.

.. tip:: If you want to test the engine, you can build with ``-DSAM_BUILD_CLI_TOOLS=ON`` and run the 
         executable. DON'T forget to add the directories you want to scan inside ``.build/sam-cli-tools/scanareasprocessor_output.pathl``
         file. You can then run the executable in the ``.build`` folder.
         .. code-block:: shell

            ./sam-cli-tools/Debug/sam-cli-tools.exe

.. tip:: Add your project build directory to the list of excluded directories of any anti-virus 
         application that runs on your system.

Linking The Console
-------------------

To link the console, you will need to run cmake with ``-DSAM_LINK_CONSOLE=ON`` and give it 
the prefix of the console's path. For example, if you want to link the console, you will run:

.. code-block:: shell

    cmake .. -G "Visual Studio 17 2022" -DSAM_STATIC_ANN_ONNX_MODELPATH="path/to/ANN-78M-in2381-h11-out1-v0.onnx" 
                                        -DSAM_STATIC_ANN_STANDARDIZE_PARAMS="path/to/standardize-params-20240307_181717.pkl" 
                                        -DSAM_STATIC_CNN_COLORMAP="path/to/gray_colormap.npy" 
                                        -DSAM_ONNXRUNTIME_ROOTDIR="path/to/onnxruntime-win-x64-1.17.1/" 
                                        -DSAM_STATIC_CNN_ONNX_MODELPATH="path/to/CNN-model3-167M-in(1,256,256)-out1.onnx" 
                                        -DSAM_LINK_CONSOLE=ON 
                                        -DCMAKE_PREFIX_PATH="C:/Qt/{QT_VERSION}/{MSVC_VERSION}/lib/cmake/"

Then run the build command:

.. code-block:: shell

    cmake --build . --config Debug

Then run the console executable in the ``.build`` folder.

.. code-block:: shell

    ./Debug/scorpion-antimalware.exe

Python Embedding
----------------

We embed Python 3.12 in our engine to run the Python scripts. You will need to get the 
packages required from the ``requirements.txt`` file in the root.

.. code-block:: shell

    pip install -r requirements.txt

.. note:: to use the Python modules with no problems, you need to make sure that 
          ``Download debug binaries`` option is checked in the Advanced ``Options``.

.. note:: Check ``Add Python to enviroment variables``` option in the installation wizard.

Running Engine's Tests
----------------------

To run the tests, you will need to run cmake with ``-DSAM_BUILD_TESTS=ON`` and then run the 
corresponding test executable in the ``.build`` folder.

.. code-block:: shell

    ./tests/Debug/sam-engine-tests.exe

You will find the command for each test case in the ``tests`` folder.
