Packaging
=========

.. highlight:: shell

Requirements
------------

For packaging under Windows, the following is required:

- `NSIS 3.10 <https://nsis.sourceforge.io/Download>`_.

.. note:: You will need the Full version of NSIS, not the Lite version or the Minimal version.

Steps
-----

1.  Run CMake and build the project in Release mode.

    .. code-block:: shell

        mkdir .build
        cd .build
        cmake -DCMAKE_BUILD_TYPE=Release ..
        cmake --build . --config Release

2.  Run the following command to create the installer:

    .. code-block:: shell

        cpack -G NSIS -C Debug

    The installer will be created in the ``.build`` directory.

