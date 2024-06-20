.. _doc_building_the_documentation:

Building the documentation with Sphinx
======================================

This page explains how to build a local copy of the Scorpion documentation using the
Sphinx docs engine. This allows you to have local HTML files and build the
documentation as a PDF, EPUB, or LaTeX file, for example.

Before you get started, make sure that you have:

- `Git <https://git-scm.com/>`_
- `make <https://www.gnu.org/software/make/>`_ (unless you're using Windows)
- `Python <https://www.python.org/>`_ 3

.. note:: Python 3 should come with the ``pip3`` command. You may need to write
    ``python3 -m pip`` (Unix) or  ``py -m pip`` (Windows) instead of ``pip3``.
    If both approaches fail, `make sure that you have pip3 installed
    <https://pip.pypa.io/en/stable/installation/>`__.

1.  Clone the docs repo:

    .. code:: sh

        git clone https://github.com/scorpionantimalware/sam-docs.git

.. note:: You can add the --depth 1 argument to omit the commit history.
          Faster, but not all Git operations (like blame) will work.

3.  Change directory into the docs repo:

    .. code:: sh

        cd sam-docs/

4.  Build the docs:

    .. code:: sh

        make html

    .. note::
        On Windows, that command will run ``make.bat`` instead of GNU Make (or an alternative).

    Alternatively, you can build the documentation by running the sphinx-build program manually:

    .. code:: sh

        sphinx-build -M html . _build/

You can then browse the documentation by opening ``_build/html/index.html`` in
your web browser.
