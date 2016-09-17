A.L.F.R.E.D - JSON Client
=========================

Compilation
-----------

alfred-json depends on:
 * libjansson
 * zlib

     $ apt-get install cmake libjansson-dev zlib1g-dev

Prepare the build using:

     $ mkdir build
     $ cd build/
     $ cmake ../

To compile, simply type:

     $ make

To install, use:

     $ make install

Usage
-----

First, an alfred daemon must be running. Data can be retrieved like this:

     $ alfred-json -r 64
    {
      "fe:f1:00:00:01:01": {
        "firmware": "0.3.2.1-1",
        "hostname": "alfredtest1"
      },
      "fe:f1:00:00:02:01": {
        "key": "value"
      }
    }

Transparent GZIP decompression
------------------------------

alfred-json will automatically and transparently decompress GZIP compressed
data when the -z option is given:

     $ echo Hello World | gzip | alfred -s 150
     $ alfred-json -z -r 150 -f string

License
-------

alfred-json is licensed under the terms of version 2 of the GNU General
Public License (GPL). Please see the LICENSE file.
