Python post-mortem debugging
============================

Pydump writes the traceback of an exception into a file and 
can later load it in a Python debugger. It works with the built-in 
pdb and with other popular debuggers (pudb, ipdb and pdbpp).

Why I wrote this?
=================

I spent way too much time trying to discern details about bugs from
logs that don't have enough information in them. Wouldn't it be nice
to be able to open a debugger and load the entire stack of the crashed
process into it and look around like you would if it crashed on your own 
machine?

Possible uses
=============

This project (or approach) might be useful in multiprocessing environments
running many unattended processes. The most common case for me is on
production web servers that I can't really stop and debug. For each 
exception caught, I write a dump file and I can debug each issue on 
my own time, on my own box, even if I don't have the source, since 
the relevant source is stored in the dump file.

Version History
===============

This fork
-----
Install it with `pip install git+git://github.com/Mikata-Project/pydump@master`

* Make it compatible with Python > 3.6
* Use zstd compression
* Add the ability to write/read to/from S3

1.2.0
-----
* Port to Python 3

1.1.1
-----
* Fixed a few small bugs.

1.1.0
-----

* Now storing built-in datatypes and custom class data members
  instead of their string representations.

1.0.0
-----

* First public version
