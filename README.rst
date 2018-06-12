#################
pfswift - v0.99
#################

.. image:: https://badge.fury.io/py/pfswift.svg
    :target: https://badge.fury.io/py/pfswift

.. image:: https://travis-ci.org/FNNDSC/pfswift.svg?branch=master
    :target: https://travis-ci.org/FNNDSC/pfswift

.. image:: https://img.shields.io/badge/python-3.5%2B-blue.svg
    :target: https://badge.fury.io/py/pfswift

.. contents:: Table of Contents

********
Overview        
********

This repository proves ``pfswift`` -- a utility module for swift access. 

pfswift
====

Most simply, ``pfswift`` provides an API and CLI for accessing a swift containerized instance.


************
Installation
************

Installation is relatively straightforward, and we recommend using either python virtual environments or docker.

Python Virtual Environment
==========================

On Ubuntu, install the Python virtual environment creator

.. code-block:: bash

  sudo apt install virtualenv virtualenvwrapper python3-tk

Then, create a directory for your virtual environments e.g.:

.. code-block:: bash

  mkdir ~/python-envs

You might want to add to your .bashrc file these two lines:

.. code-block:: bash

    export WORKON_HOME=~/python-envs
    source /usr/local/bin/virtualenvwrapper.sh

Then you can source your .bashrc and create a new Python3 virtual environment:

.. code-block:: bash

    source .bashrc
    mkvirtualenv --python=python3 --system-site-packages python_env

To activate or "enter" the virtual env:

.. code-block:: bash

    workon python_env

To deactivate virtual env:

.. code-block:: bash

    deactivate

Using the ``fnndsc/ubuntu-python3`` dock
========================================

We provide a slim docker image with python3 based off Ubuntu. If you want to play inside this dock and install ``pfswift`` manually, do

.. code-block:: bash

    docker pull fnndsc/ubuntu-python3

This docker has an entry point ``python3``. To enter the dock at a different entry and install your own stuff:

.. code-block:: bash

   docker run -ti --rm --entrypoint /bin/bash fnndsc/ubuntu-python3
   
Now, install ``pfswift`` and friends using ``pip``

.. code-block:: bash

   apt update && \
   apt install -y libssl-dev libcurl4-openssl-dev librtmp-dev && \
   pip install pfswift
   
**If you do the above, remember to** ``commit`` **your changes to the docker image otherwise they'll be lost when you remove the dock instance!**

.. code-block:: bash

  docker commit <container-ID> local/ubuntu-python3-pfswift
  
 where ``<container-ID>`` is the ID of the above container.
  

Using the ``fnndsc/pfswift`` dock
=================================

The easiest option however, is to just use the ``fnndsc/pfswift`` dock.

.. code-block:: bash

    docker pull fnndsc/pfswift
    
and then run

.. code-block:: bash

    docker run --name pfswift -v /home:/Users --rm -ti fnndsc/pfswift

*****
Usage
*****

``pfswift`` usage
===============

For ``pfswift`` detailed information, see the `pfswift wiki page <https://github.com/FNNDSC/pfswift/wiki/pfswift-overview>`_.

