Note: This project is discontinued and the code remains here for example/learning purposes.

Modern-openZWave
==========

A modern implementation of the openzwave library in C++11 which implements a JSON frontend controlled through zeromq who delivers a easy to use socket over TCP, IPC and more. 

Currently, the data send from the modernozw(modern-openZWave) server are dead simple to parse and understand, you just need to know what an nodeID, homeID and the specifications of the node itself are. The controll set currently includes the following commands (soon to be extended if neccesary)
        
        {'home_id':1, 'node_id' : 1, 'value': True}
Which (suprise, suprise) sets the switch value of node 1 in home 1 to True. The home_id is optional! Currently we do not support an extensive set of openZWave commands and I highly encourage you to use https://www.domotiga.nl/ or https://code.google.com/p/openzwave-control-panel/ for extensive debugging of the node/home settings. I will however add bindings for the command set in the coming week.

Installation Raspberry pi:
-----
For Rasbian users do the following steps:
        
        
    sudo apt-get install libzmq-dev libudev-dev
    cd ~
    git clone https://github.com/merijntestroote/modern-openZWave.git
    cd modern-openZWave/
    ./install-rpi.sh

It might promt you for your password at different stages. When everything ran correctly you should be able to plug in your zwave device and launch up ./ModernOZW and start hacking :)
 
Installation:
-----
For ubuntu/debian users install this:
        
    sudo apt-get install subversion libudev-dev libzmq-dev

Then run ./install.sh (this assumes you have sudo installed and sudo rights on the current user). 
After installing you have the ModernOZW executable :) The installation (compilation) might take some time on devices
like the Raspberry pi.

If you have already installed open-zwave you can copy the compiled directory to the modern-openZWave directory or you can specify the header files and the library in the src/Makefile.


Features/Working:
-----
- Getting values from nodes.
- Setting values in nodes.
- JSON control through zeromq (see the python directory for receive and set examples).
- When the zwave adapter is detached we automatically exit, default openzwave implementations do not.
- Install script for compiling openZWave and Modern-openZWave


Todo:
-----
- Test the installation script on Debian, Automate zeromq installation on non archlinux distro's
- Comment and document code
- Complete the hook system

Contact
-----
merijn (a) nullbyte (.) nl

License:
-----
This project is a full rewrite of the MinOZW example in the OpenZWave library. The idea is to allow programmers to quickly implement this and use ZWave without any troubles. All the including files EXCEPT the Makefile, jsoncpp library and the openzwave library fall under the following license.


    Copyright (C) 2014  Merijn Testroote

    This program is free software; you can redistribute it and/or modify
    it under the terms of the GNU General Public License as published by
    the Free Software Foundation; either version 2 of the License, or
    (at your option) any later version.

    This program is distributed in the hope that it will be useful,
    but WITHOUT ANY WARRANTY; without even the implied warranty of
    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
    GNU General Public License for more details.

    You should have received a copy of the GNU General Public License along
    with this program; if not, write to the Free Software Foundation, Inc.,
    51 Franklin Street, Fifth Floor, Boston, MA 02110-1301 USA.

