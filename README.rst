blepy
=====

Python bindings for Bluegiga BLED112 Bluetooth Low Energy USB Dongle.

This project generates python api bindings for the Bluegiga BLED112 by parsing
the bleapi XML specification file. The user is required to have the Bluegiga
Bluetooth Smart SDK (available from http://techforum.bluegiga.com/BLED112). 
This project is in no way associated with Bluegiga.


Caveats
-------

This is a work in progress and probably won't "just work". It has been tested 
so far on Mac OS X and Raspberry Pi. Sending variable length messages is currently not implemented properly.


Api Generation
--------------

#. Install python prerequisites; numpy and ctypes (possibly already available
   on your system)

#. Run ``api_gen.py <XML file>`` where <XML file> is the file "bleapi.xml" found
   in the "api" folder of the Bluegiga SDK. This will generate "ble.py"
   
#. Compile the uart module (which is imported into "ble.py" by ctypes). This
   requires the "uart.c" and "uart.h" files from SDK/src/thermometer-demo
   
   ``gcc -o uart.so uart.c -shared``
   
#. Copy the "uart.so" file to the same location as "ble.py" 


Usage
-----
 
Take a look at "demo.py" to get an idea of how to use the library






