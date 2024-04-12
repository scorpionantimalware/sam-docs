.. _doc_compiling_console_for_windows:

Compiling Console for Windows
=============================

.. highlight:: shell

Requirements
------------

For compiling under Windows, the following is required:

- `Visual Studio Community <https://www.visualstudio.com/vs/community/>`_. VS 2022 
  is recommended.
- `Qt6 <https://www.qt.io/download-open-source>`_. VS 2022 
  is recommended.
- `CMake 3.5+ <https://cmake.org/download/>`_ build system.

.. seealso:: To get the Scorpion source code for compiling, see
             :ref:`doc_getting_source`.

..             For a general overview of CMake usage for Scorpion, see
..             :ref:`doc_sam_buildsystem`.

             Check :ref:`doc_compiling_engine_for_windows` for general 
             instructions on compiling engine for Windows.

Setting up CMake
----------------

To install CMake, download the installer from the `CMake website <https://cmake.org/download/>`_ and run it.

You can then check that CMake is installed by running ``cmake --version`` in a command prompt.

.. _doc_compiling_console_for_windows_install_vs:

Downloading Console's source
----------------------------

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
    cmake .. -G "Visual Studio 17 2022" -DCMAKE_PREFIX_PATH="C:/Qt/{QT_VERSION}/{MSVC_VERSION}/lib/cmake/"

You can build then with:

.. code-block:: shell

    cmake --build . --config Debug

Then you can run by:

.. code-block:: shell

    ./Debug/sam-console.exe

.. note:: The console uses a dummy engine so you don't need to worry about the 
          engine's build. This is for faster compilation as the engine is not needed 
          for developing the console.

.. note:: You can find our models at `SAM Models <https://drive.google.com/drive/folders/1frJ8Pll8AdRHpTnSHSCPZEVvOz_FHSRT?usp=sharing>`_.

If all goes well, you will have our engine's ``.lib`` and ``.dll`` files in the ``.build`` folder.

.. tip:: Add your project build directory to the list of excluded directories of any anti-virus 
         application that runs on your system.
