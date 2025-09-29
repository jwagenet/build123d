############
Installation
############

Python Versions
==============================

**build123d** supports Python 3.10 to 3.13.

Virtual Environment
==============================

Using a virtual environment is highly recommended to avoid Python version and package
compatibility issues with other Python projects.

Create and activate environment
-------------------------------

.. tab-set::
    :sync-group: os

    .. tab-item:: Linux/macOS
        :sync: linux-macos

        .. code-block::

            $ mkdir cadproject
            $ cd cadproject
            $ python3 -m venv .venv
            $ . .venv/bin/activate

    .. tab-item:: Windows
        :sync: windows

        .. code-block::

            > mkdir cadproject
            > cd cadproject
            > py -3 -m venv .venv
            > .venv\Scripts\activate

Install Current Release
==============================

Installing **build123d** releases from `PyPI <https://pypi.org/project/build123d/>`_
using ``pip`` is recommended for most users.

.. tab-set::
    :sync-group: pkgmgr

    .. tab-item:: pip
        :sync: pip

        .. code-block::

            pip install build123d

    .. tab-item:: poetry
        :sync: poetry

        .. code-block::

            poetry add build123d

.. note::

	The viewer `ocp-vscode <https://github.com/bernhard-42/vscode-ocp-cad-viewer>`_
        can install **build123d** with the ``OCP CAD Viewer`` VS Code extension.

Install Latest
==============================

**build123d** is under active development. To use up-to-date features and changes install
the latest updates in the development branch from
`GitHub <https://github.com/gumyr/build123d>`_.

.. tab-set::
    :sync-group: pkgmgr

    .. tab-item:: pip
        :sync: pip

        .. code-block::

            pip install git+https://github.com/gumyr/build123d

    .. tab-item:: poetry
        :sync: poetry

        .. code-block::

            poetry add git+https://github.com/gumyr/build123d.git@dev

        .. note::

	        **build123d** uses a ``dev`` branch rather than ``main`` or ``master``, as
                specified above for safety

Test Installation
=============================================

To verify installation, run the following snippet in a command line Python REPL. The
expected output is a tree of topological objects for a box beginning with a parent ``Solid``.

.. code-block::

	>>> from build123d import *
	>>> print(Solid.make_box(1,2,3).show_topology(limit_class="Face"))
		Solid        at 0x165e75379f0, Center(0.5, 1.0, 1.5)
		└── Shell    at 0x165eab056f0, Center(0.5, 1.0, 1.5)
			├── Face at 0x165b35a3570, Center(0.0, 1.0, 1.5)
			├── Face at 0x165e77957f0, Center(1.0, 1.0, 1.5)
			├── Face at 0x165b3e730f0, Center(0.5, 0.0, 1.5)
			├── Face at 0x165e8821570, Center(0.5, 2.0, 1.5)
			├── Face at 0x165e88218f0, Center(0.5, 1.0, 0.0)
			└── Face at 0x165eb21ee70, Center(0.5, 1.0, 3.0)

Viewers and User Interfaces
=============================================

The most popular viewer `ocp-vscode <https://github.com/bernhard-42/vscode-ocp-cad-viewer>`_
has a VS Code extension for integrated development, but also supports standalone use
in a web browser for development in a preferred editor.

Other viewers and user interfaces an be found in :ref:`external`.

Getting Help
=============================================

Need to ask a question or want to share a project? Find an active community of
developers and users on:

* `Discord <https://discord.com/invite/Bj9AQPsCfx>`_; most active, shared with CadQuery
* `GitHub Discussions <https://github.com/gumyr/build123d/discussions>`_

Contributing
=============================================

**build123d** accepts issue and code contributions on
`GitHub <https://github.com/gumyr/build123d>`_. See
`CONTRIBUTING.md <https://github.com/gumyr/build123d/blob/dev/CONTRIBUTING.md>`_ for
full setup of development environment and contribution requirements.

Install in development mode
---------------------------

With up-to-date ``pip``, install **build123d** in
`development mode <https://setuptools.pypa.io/en/latest/userguide/development_mode.html>`_
from a clone of the ``git`` repository to a virtual environment. Development mode loads
the package changes from the development folder.

.. code-block::

	git clone https://github.com/gumyr/build123d.git
	cd build123d
	pip install -e .
