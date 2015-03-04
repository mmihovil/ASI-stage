Serial Pack 2.0
  National Instruments LabVIEW® 7.0 VI's for controlling 
  ASI's MS-2000 Controller through a Windows® Serial Port.

Copyright © 2004 by ASI
  Released 3/17/2004

Contact: 
  Spencer Doidge
  Software Engineer, ASI
  spencer@ASIimaging.com
  Office phone: 541-461-8181 ext 16


Controlling MS-2000 from the computer
-------------------------------------
MS-2000 controllers can respond to commands received through its serial port. 
Even with an MS-2000 connected to a computer's serial port, you may still 
operate the controller independent from the computer.  

You can issue MS-2000 commands by typing them at your computer keyboard and 
causing them to be sent to the serial port using DOS commands. You can use 
any serial port program. At ASI, we use Windows® HyperTerminal® every day.

You can also use the enclosed LabVIEW® VI's to send commands and receive 
replies with your LabVIEW® programs.  


This text file explains how to set up your system to operate with the serial 
port. It also describes the enclosed VI's.

For a complete explanation of the commands, consult our manual:
http://www.asiimaging.com/ftp2asi/Manuals/MS2000%20Programming.pdf

The "PROGRAMMING" manual section explains commands that you can use to control 
MS-2000 from the computer keyboard or from your programs.


Serial Port Setup with MS-2000
-------------------------------

To use the serial port with the MS2000, use *ONLY* the ASI Serial Null 
Modem Cable.  Connect the male end to the MS-2000 connector labeled 
"RS232 SERIAL IN." Connect the female end to your computer's serial port.  
DIP switches 4 and 5 located on the MS-2000's back panel should be in the 
UP position.  

These VI's are currently configured to use COM1.  They can be edited to use 
another port if necessary.  

Port settings are COM1, 9600 baud, 8 data bits, 1 stop bit, no parity, no flow control.  
Additional HyperTerminal® 'Property Settings' for 'ASCII Setup' are "Echo typed 
characters locally" and, optionally, "Append line feeds to incoming line ends".

If you need more help setting up HyperTerminal® for MS-2000, call ASI.


Testing the Serial Port with MS-2000
------------------------------------
You may use these VI's and/or Windows® HyperTerminal®.

We recommend using HyperTerminal® for interactive and diagnostic sessions, 
although SerialComplexInteractive.vi also works for that.  

A simple test:  When an MS-2000 and HyperTerminal® or 
SerialComplexInteractive.vi are properly connected and set up, pressing 
<Enter> causes MS-2000 to reply with the string ":N-1".  


National Instruments LabVIEW® VI's included in this package
------------------------------------------------------------
Self-contained one-VI solutions:
    These three VI's use only LabVIEW® built-in functions as sub-VI's.
	
    SerialMoveXY.vi - Connects, moves X and Y axes, waits for completion of move, disconnects.
    SerialMoveZ.vi  - Connects, moves Z axis, waits for completion of move, disconnects.
    SerialWhere.vi  - Connects, issues WHERE command to input axis, returns axis position in 
                      10ths of micron, disconnects.
    Note: Connecting and disconnecting is fast enough so that these VI's are recommended for
          normal applications.

Example interactive applications:

    SerialComplexInteractive.vi  - Emulates HyperTerminal®.
    SerialSimpleInteractive.vi   - Sends hand-typed commands, ignores replies.

    Sub-vi's:

        SerialConnect.vi        - opens serial port
        SerialDisconnect.vi     - closes serial port
        WriteCmd.vi             - concatenates CR LF to a command, transmits
        SerialWaitForStatusN.vi - sends STATUS commands up to a max number of tries (default=400),
                                  returns Success = TRUE if it receives 'N' (i.e., not busy).

    Readme.txt  - this file

<end of file>
