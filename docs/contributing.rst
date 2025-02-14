Cosmos Contributing Guide
=========================

All contributions, bug reports, bug fixes, documentation improvements, enhancements are welcome.

As contributors and maintainers to this project, you are expected to abide by the
`Contributor Code of Conduct <https://github.com/astronomer/astronomer-cosmos/blob/main/CODE_OF_CONDUCT.md>`_.

Overview
________

To contribute to the cosmos project:

#. Please create a `GitHub Issue <https://github.com/astronomer/astronomer-cosmos/issues>`_ describing your contribution
#. Open a feature branch off of the ``main`` branch and create a Pull Request into the ``main`` branch from your feature branch
#. Link your issue to the pull request
#. Once developments are complete on your feature branch, request a review and it will be merged once approved.

Creating a Sandbox to Test Changes
__________________________________

Pre-requisites
**************
#. `tilt <https://docs.tilt.dev>`_
#. `git <https://git-scm.com/book/en/v2/Getting-Started-Installing-Git>`_

Local Sandbox
************

For local development, we use `Tilt <https://docs.tilt.dev>`_. To use Tilt, first clone the ``astronomer-cosmos`` repo:

.. code-block:: bash

    git clone https://github.com/astronomer/astronomer-cosmos.git

Then, run the following from the ``astronomer-cosmos`` directory:

.. code-block:: bash

    tilt up

You can press ``space`` to open the Tilt UI and see the status of the sandbox. Once the sandbox is up, you can access the Airflow UI at ``http://localhost:8080``.


Pre-Commit
************

We use pre-commit to run a number of checks on the code before committing. To install pre-commit, run:

.. code-block:: bash

    pre-commit install

To run the checks manually, run:

.. code-block:: bash

    pre-commit run --all-files


Writing Docs
__________________________________

You can run the docs locally by running the following:

.. code-block:: bash

    hatch run docs:serve


This will run the docs server in a virtual environment with the right dependencies. Note that it may take longer on the first run as it sets up the virtual environment, but will be quick on subsequent runs.


Building
__________________________________

We use `hatch <https://hatch.pypa.io/latest/>`_ to build the project. To build the project, run:

.. code-block:: bash

    hatch build


Releasing
__________________________________

We use GitHub actions to create and deploy new releases. To create a new release, first create a new version using:

.. code-block:: bash

    hatch version minor


hatch will automatically update the version for you. Then, create a new release on GitHub with the new version. The release will be automatically deployed to PyPI.

.. note::
    You can update the version in a few different ways. Check out the `hatch docs <https://hatch.pypa.io/latest/version/#updating>`_ to learn more.
