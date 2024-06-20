.. _doc_getting_source:

Getting the source
==================

.. highlight:: shell

Downloading the Scorpion source code
------------------------------------

.. Before :ref:`getting into the CMake build system <doc_sam_buildsystem>`
.. and compiling Scorpion, you need to actually download the Scorpion source code.

The source code is available on 
`scorpionantimalware/scorpion-antimalware <https://github.com/scorpionantimalware/scorpion-antimalware>`_
and while you can manually download it via the website, in general you want to
do it via the ``git`` version control system.

If you don't know much about ``git`` yet, there are a great number of
`tutorials <https://git-scm.com/book>`_ available on various websites.

In general, you need to install ``git`` and/or one of the various GUI clients.

Afterwards, to get the latest development version of the Scorpion source code
(the unstable ``master`` branch), you can use 
``git clone --recurse-submodules --depth 1 --shallow-submodules https://github.com/scorpionantimalware/scorpion-antimalware.git``.

If you are using the ``git`` command line client, this is done by entering
the following in a terminal:

::

    git clone https://github.com/scorpionantimalware/scorpion-antimalware.git
    # You can add the --depth 1 argument to omit the commit history.
    # Faster, but not all Git operations (like blame) will work.

.. After downloading the Scorpion source code,
.. you can :ref:`continue to compiling Scorpion <doc_sam_buildsystem>`.

.. note:: DON'T forget to clone the submodules after cloning the repository. You can do this by running the following command:
          ``git submodule update --init``

Downloading the Console source code
-----------------------------------

The source code is available on 
`scorpionantimalware/sam-console <https://github.com/scorpionantimalware/sam-console>`_
and while you can manually download it via the website, in general you want to
do it via the ``git`` version control system using the following command:
``git clone --recurse-submodules --depth 1 --shallow-submodules https://github.com/scorpionantimalware/sam-console.git``.

