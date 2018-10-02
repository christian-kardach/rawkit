rawkit
======

.. image:: https://badge.fury.io/py/rawkit.svg?
  :alt: Package Status
  :target: https://pypi.python.org/pypi/rawkit

.. image:: https://readthedocs.org/projects/rawkit/badge/?version=latest
   :alt: Docs Status
   :target: https://rawkit.readthedocs.org/en/latest/

.. image:: https://secure.travis-ci.org/photoshell/rawkit.svg?branch=master
   :alt: Build Status
   :target: https://travis-ci.org/photoshell/rawkit

.. image:: https://img.shields.io/coveralls/photoshell/rawkit.svg?style=flat
   :alt: Test Coverage Status
   :target: https://coveralls.io/r/photoshell/rawkit

.. image:: https://img.shields.io/badge/license-MIT-blue.svg
   :alt: MIT License
   :target: https://github.com/photoshell/rawkit/blob/master/LICENSE

.. note::

   `rawkit` is still alpha quality software. Until it hits 1.0, it may undergo
   substantial changes, including breaking API changes.

``rawkit`` is a :mod:`ctypes`-based set of LibRaw_ bindings for Python inspired
by Wand_. It is licensed under the `MIT License`_.

.. sourcecode:: python

    from rawkit.raw import Raw
    from rawkit.options import WhiteBalance

    with Raw(filename='some/raw/image.CR2') as raw:
      raw.options.white_balance = WhiteBalance(camera=False, auto=True)
      raw.save(filename='some/destination/image.ppm')

.. _LibRaw: http://www.libraw.org/
.. _Wand: http://docs.wand-py.org
.. _MIT License: https://github.com/photoshell/rawkit/blob/master/LICENSE

Requirements
------------

- Python

  - CPython 2.7+
  - CPython 3.5+
  - PyPy 2.5+
  - PyPy3 2.4+

- LibRaw

  - LibRaw 0.16.x
  - LibRaw 0.17.x
  - LibRaw 0.18.x
  - LibRaw 0.19.x

Installing rawkit
-----------------

First, you'll need to install LibRaw:

  - `libraw` or `libraw16`_ on Arch_
  - `LibRaw` on Fedora_ 21+ and EPEL 6
  - `libraw-bin` on Ubuntu_ trusty+
  - `libraw-bin` on Debian_ Jessie+

Now you can fetch rawkit from PyPi_:

.. sourcecode:: bash

    $ pip install rawkit

.. _`libraw16`: https://aur.archlinux.org/packages/libraw16/
.. _Arch: https://www.archlinux.org/packages/extra/x86_64/libraw/
.. _Fedora: https://apps.fedoraproject.org/packages/LibRaw
.. _Ubuntu: https://packages.ubuntu.com/bionic/libraw-bin
.. _Debian: https://packages.debian.org/stable/graphics/libraw-bin
.. _PyPi: https://pypi.python.org/pypi/rawkit

Tutorials
---------

.. toctree::
   :glob:
   :maxdepth: 1

   tutorials/*

Architecture and Design
-----------------------

.. toctree::
   :glob:
   :maxdepth: 1

   design/*

API Reference
-------------

The `rawkit` package provides two modules: `rawkit` and `libraw`. The `rawkit`
module provides a high-level Pythonic interface for developing raw photos,
while the `libraw` module provides a CTypes based interface for interacting
with the low-level LibRaw C APIs. Most of the time, developers will want to use
the `rawkit` module instead of using `libraw` directly.

.. toctree::
   :maxdepth: 1

   api/modules
   api/libraw
   api/rawkit

Indices and tables
------------------

* :ref:`genindex`
* :ref:`modindex`
* :ref:`search`
