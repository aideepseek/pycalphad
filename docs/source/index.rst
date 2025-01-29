.. meta::
    :google-site-verification lang=en:
        yV82IoMAddNFvTOfoE9B9lcnmu01sA7HglIob1l1jzY

Pycalphad Installation Guide
============================

Pycalphad is a Python library for thermodynamic modeling, phase diagram calculation, and phase equilibrium investigations using the CALPHAD method. Follow the instructions below to install pycalphad based on your preferred method.

Installation with pip (Recommended)
------------------------------------

To install pycalphad from PyPI using pip:

.. code-block:: bash

   pip install -U pip setuptools
   pip install -U pycalphad

**Using a Virtual Environment**

It is recommended to install pycalphad within a virtual environment for better dependency management. To create and activate an environment called `pycalphad-env` on Linux or macOS:

.. code-block:: bash

   python -m venv pycalphad-env
   source pycalphad-env/bin/activate
   pip install -U pip setuptools
   pip install -U pycalphad

.. note::
   The virtual environment must be activated every time you use pycalphad.

Installation with conda
-----------------------

`Anaconda` is a popular platform for scientific Python packages. If you don’t have Anaconda installed, you can download the Miniconda distribution.

To install pycalphad from conda-forge using `conda`:

.. code-block:: bash

   conda install -c conda-forge pycalphad

Installing the Development Version
-----------------------------------

The source code for the latest development version of pycalphad is available on GitHub. A working version of `git` and a C++ compiler is required to install the development version.

**Windows Requirements:**
Install `git` and Microsoft Visual C++ Build Tools version 14.X. Tutorials are available online to guide you through the process.

**Steps to Install the Development Version:**

1. Clone the repository:

   .. code-block:: bash

      git clone https://github.com/pycalphad/pycalphad.git
      cd pycalphad

2. Install the dependencies and the package:

   .. code-block:: bash

      pip install -U pip setuptools
      pip install -U -r requirements-dev.txt
      pip install -U --no-build-isolation --editable .

3. Run automated tests to ensure everything is installed correctly:

   .. code-block:: bash

      pytest pycalphad

**Upgrading Development Version:**

Changes to Python files (`.py`) in an editable install will take effect immediately upon saving. However, changes to Cython files (`.pyx` and `.pxd`) must be recompiled using:

.. code-block:: bash

   python setup.py build_ext --inplace

**Updating the Development Version:**

To update the code to the latest changes in the current branch:

.. code-block:: bash

   git pull

To switch to a different branch (e.g., `master` for the latest released version or another feature branch):

.. code-block:: bash

   git checkout <branch>

.. note::
   Replace `<branch>` with the name of the branch you want to switch to.

Root Directory Definition
-------------------------

The "root directory" refers to the top-level project directory containing:

- `pyproject.toml` file
- `pycalphad/` package directory

Ensure you are in the root directory when running build commands.

.. toctree::
   :maxdepth: 2
   :caption: Quick Start

   examples/metastability
