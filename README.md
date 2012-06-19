linpdir-poc
===========

Proof of concept of an [Input Director][] (ID) slave. Written in Python.

Based on the protocol info from [uix5/info-inpdir][]. Work in progress.

I'm also not really a Python programmer :s.

uix5 (c) 2012


Rationale
---------

As a fan of ID, I needed to direct a slave running Ubuntu, but unfortunately
ID supports only Windows. I didn't want to migrate to Synergy just for this
single slave, so I wrote this.


State
-----

 * no support for encryption
 * no support for master operation (it's a slave)
 * no support for clipboard sync
 * no support for hiding the mouse cursor
 * no proper check for master 'authentication'
 * no gui or settings panel (in fact, barely any settings at all)
 * no support for running-as-daemon
 * only supports US International keyboard layout
 * only tested on Ubuntu Lucid and Oneiric
 * not tested with multiple displays on either master or slave
 * probably / likely lots of bugs


Dependencies
------------

 * Python 2.6+
 * twisted
 * [python-uinput][] 0.6+ (make sure it works)
 * [python-xlib][] 0.15+


Installation
------------

 1. Clone repository
 2. Satisfy dependencies (use pip or something else)
 3. start `linpdir-poc.py` in a terminal

`ctrl+c` stops the slave.


Known Issues
------------

 * always: mouse cursor transition checks are currently based on just the mouse 
   coordinates. This can result in some strange transitioning behaviour on the
   slave.
   Input Director seems to also look at cursor velocity (dx, dy).


Acknowledgement
---------------

[Input Director][] v1.2.2 is (c) 2010 Imperative Software Pty Ltd. It's a great
util without which this wouldn't have been possible. No reverse-engineering
of ID binaries or associated libraries was ever performed (nor needed).





[Input Director]:   http://www.inputdirector.com/
[uix5/info-inpdir]: https://github.com/uix5/info-inpdir
[python-uinput]:    http://tjjr.fi/sw/python-uinput/
[python-xlib]:      http://python-xlib.sourceforge.net/
