# Python script to control the APC power cycler

For now, it is compatible with python 2.7. Will move it to python 3 soon.

To view the help:
=================

$ python apc.py -h
usage: apc.py [-h] [--host HOST] [--user USER] [--password PASSWORD] [-v]
              [--quiet] [--debug] [--reboot REBOOT] [--off OFF] [--on ON]
              [--get GET]

APC Python CLI

optional arguments:
  -h, --help           show this help message and exit
  --host HOST          Override the host
  --user USER          Override the username
  --password PASSWORD  Override the password
  -v, --verbose        Verbose messages
  --quiet              Quiet
  --debug              Debug mode
  --reboot REBOOT      Reboot an outlet
  --off OFF            Turn off an outlet
  --on ON              Turn on an outlet
  --get GET            Get the status of an outlet. Enter number 1 to 8 or all

To get the status of a single powet outlet:
===========================================

$ python apc.py --get 1
Acquiring lock /tmp/apc.lock
Connecting to APC @ 192.168.9.6
olStatus 1
E000: Success
 1: Switch 2108B: On
DISCONNECTED from 192.168.9.6

To get the status of all the outlets:
=====================================

$ python apc.py --get all
Acquiring lock /tmp/apc.lock
Connecting to APC @ 192.168.9.6
olStatus all
E000: Success
 1: Switch 2108B: On
 2: Switch 3329: On
 3: Switch 2188 A: On
 4: Switch 2188 B: On
 5: Switches 135/137: On
 6: Switch 1790: On
 7: Switch 2108A: On
 8: Switch 1820: On

apc>olStatus all

DISCONNECTED from 192.168.9.6
