.. highlight:: console
.. author:: Florenz <fl@well.com>

.. tag:: lang-python
.. tag:: lang-django
.. tag:: lang-node
.. tag:: web
.. tag:: file-storage

.. sidebar:: Logo

  .. image:: _static/images/archivebox.png
      :align: center

##########
Archivebox
##########

.. tag_list::

Archivebox_ is an open source archiving solution, your personal archive.org

----

.. note:: For this guide you should be familiar with the basic concepts of

  * :manual:`Python <lang-python>`
  * :manual:`domains <web-domains>`

Prerequisites
=============

Use the recommended :manual:`Python <lang-python>` version as listed in the `system requirements`_:

You can use the domains that are currently configured :

.. include:: includes/web-domain-list.rst

If you want to use a domain not shown here, :manual:`setup your domain <web-domains>` for use with your Uberspace account.

Installation
============

Install with pip
----------------

.. code-block:: console

  [isabell@stardust ]$ pip install --user archivebox

TODO: symlink to log directory

Initialize the environment
^^^^^^^^^^^^^^^^^^^^^^^^^^

Create a data directory to keep the archived websites and metadata, and change to it with `cd`. Then initialize a fresh Archivebox repository:

.. code-block:: console

  [isabell@stardust ]$ mkdir -p archivebox/data
  [isabell@stardust ]$ cd archivebox/data
  [isabell@stardust data]$ archivebox init
  [isabell@stardust data]$

Except for the initialization commands, Archivebox always acts on the current directory, please make sure that you change to the data directory before executing archivebox commands.

Run the setup script
^^^^^^^^^^^^^^^^^^^^

In a newly initialized data directory, run the `setup` command to run the auto-detection for the tools Archivebox requires:

.. code-block:: console

    [isabell@stardust ]$ cd archivebox/data
    [isabell@stardust data]$ archivebox setup

The output should not show errors. Requirements that are not detected will not be usable for this Archivebox instance.

Start Archiving
===============

Start manually
^^^^^^^^^^^^^^

To manually start Archivebox, activate the Python virtual environment, change to the data directory and run `archivebox server`:

.. code-block:: console

    (venv) [isabell@stardust data]$ archivebox server
    [i] [2024-12-02 19:05:40] ArchiveBox v0.7.2: archivebox server

    [+] Starting ArchiveBox webserver...
        > Logging errors to ./logs/errors.log
    Performing system checks...

    System check identified no issues (0 silenced).
    December 02, 2024 - 19:05:42
    Django version 3.1.14, using settings 'core.settings'
    Starting development server at http://127.0.0.1:8000/
    Quit the server with CONTROL-C.

Logon to the Archivebox webinterface, and archive your first website


Archive a website
^^^^^^^^^^^^^^^^^

Run automatically
^^^^^^^^^^^^^^^^^

Configuration
=============
archivebox set

Updates
=======

Troubleshooting
===============

----

Tested with Archivebox v x.y.z on Uberspace 7 with Python 3

.. author_list::
