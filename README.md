# getdevinfo

This repository holds the getdevinfo module. This module was originally integreted directly into the source code of Wine Autostart, DDRescue-GUI, and WxFixBoot, but has now been separated for ease of maintenance. This version is for legacy Mac OS X 10.5 (PowerPC) and 10.6 (32-bit Intel). Mac OS X 10.6 - 10.9 (64-bit Intel) are also supported pending testing.

Other platforms are not supported. Please use the latest version of getdevinfo at https://gitlab.com/hamishmb/getdevinfo for newer and other platforms.

This version is only supported on Python 2, but may work on Python 3 as well.

Description of Package
======================
A device information gatherer for Linux and macOS.

Working on both Linux and macOS, this script makes use of lshw, lvdisplay, and blkid (Linux), as well as diskutil (macOS) to get a comprehensive amount of disk information. This information is available in a structured dictionary for ease of use.

Features:
---------

Uses the operating system\'s built-in tools to gather lots of helpful information about disks connected to the system. This is returned as a hierarchical python dictionary. For the full details on the format, read the documentation here: https://www.hamishmb.com/html/Docs/getdevinfo.php

Dependencies:
-------------

On Linux it requires lshw, blkid, lvdisplay, and blockdev to be installed. On Linux, you need the beautifulsoup4 (bs4), and lxml python packages to use this tool. On macOS, nothing beyond a standard python2.x/python3.x install is required, but you still need bs4 and lxml if you want to install using the python wheel/through pip.

Building
========

Source Distribution
-------------------

Run:

"python2 setup.py sdist"

Wheels
------

Make sure you've installed the "wheel" package:

"pip/pip2 install wheel"

Pure Python Wheel
-----------------

The recommended way to create a wheel on this version of GetDevInfo:

"python2 setup.py bdist_wheel"


Distribution Packages
=====================

Distribution packages are not provided for this version of getdevinfo, as it is intended for use in DDRescue-GUI bundles for legacy Macs. If you require 

Documentation
=============
This can be found at https://www.hamishmb.com/html/Docs/getdevinfo.php.

Running The Tests
=================

These have to be run as the superuser, because low-level access to hardware is required to gather information.

Without Coverage Reporting
--------------------------
Change directory to the getdevinfo subfolder, and run:

"sudo python2 ./tests.py"

With Coverage Reporting
-----------------------
Make sure you have installed Coverage.py using pip or your package manager.

Change directory to the getdevinfo subfolder, and run:

"sudo python2 -m coverage run --rcfile=../.coveragerc ./tests.py"

To run the tests. Then run:

"sudo python2 -m coverage report"

or:

"sudo python2 -m coverage report"

To see the report.
