# Arduino-Cores
Installing
==========

__Boards Manager__


This is the suggested installation method for end users.

Prerequisites

-  Arduino 1.6.8, get it from [Arduino Website](https://www.arduino.cc/en/Main/OldSoftwareReleases#previous) .
-  Internet connection

Instructions -(Windows)
-----------
~~~~~~~~~~~~

-  Start Arduino and open Preferences window.
-  Enter into *Additional Board Manager URLs* field. You can add multiple
   URLs, separating them with commas.
-  Open Boards Manager from Tools > Board menu and find *esp8266*
   platform.
-  Select the version you need from a drop-down box.
-  Click *install* button.
-  Don't forget to select your ESP8266 board from Tools > Board menu
   after installation.
~~~~~~~~~~~~~
For more information on the Arduino Board Manager, see:

- [https://www.arduino.cc/en/guide/cores](https://www.arduino.cc/en/guide/cores)

   ..code:: bash
      
       cd %USERPROFILE%\Documents\Arduino\
       if not exist hardware mkdir hardware
       cd hardware
       if not exist esp8266com mkdir esp8266com
       cd esp8266com
       git clone []https://github.com/esp8266/Arduino.git esp8266

   You should end up with the following directory structure in
   
   ``C:\Users\{your username}\Documents\``

   ..code:: bash

       Arduino
       |
       --- libraries
       --- hardware
           |
           --- esp8266com
               |
               --- esp8266
                   |
                   --- bootloaders
                   --- cores
                   --- doc
                   --- libraries
                   --- package
                   --- tests
                   --- tools
                   --- variants
                   --- platform.txt
                   --- programmers.txt
                   --- README.md
                   --- boards.txt
                   --- LICENSE

Initialize the submodules
----------

   ..code:: bash

       cd %USERPROFILE%\Documents\Arduino\hardware\esp8266com\esp8266
       git submodule update --init   
  
  If error messages about missing files related to ``SoftwareSerial`` are encountered during the build process, it should be because this step was missed and is required.
  
__Download binary tools__
```
   ..code:: bash

       cd esp8266/tools
       python get.py
```
- Restart Arduino

- If you are using the Arduino IDE for [Visual Studio](https://www.visualmicro.com/), be sure to click Tools - Visual Micro - Rescan Toolchains and Libraries 

-  When later updating your local library, goto the esp8266 directory and do a git pull
```
   .. code:: bash

       cd %USERPROFILE%\Documents\Arduino\hardware\esp8266com\esp8266
       git status
       git pull
```
Note that you could, in theory install in ``C:\Program Files (x86)\Arduino\hardware`` however this has security implications, not to mention the directory often gets blown away when re-installing Arduino IDE. It does have the benefit (or drawback, depending on your perspective) - of being available to all users on your PC that use Arduino.

__Instructions - Other OS__

-  Open the console and go to Arduino directory. This can be either your
   *sketchbook* directory (usually ``<Documents>/Arduino``), or the
   directory of Arduino application itself, the choice is up to you.
-  Clone this repository into hardware/esp8266com/esp8266 directory.
   Alternatively, clone it elsewhere and create a symlink, if your OS
   supports them.

   .. code:: bash

       cd hardware
       mkdir esp8266com
       cd esp8266com
       git clone https://github.com/esp8266/Arduino.git esp8266

   You should end up with the following directory structure:

   .. code:: bash

       Arduino
       |
       --- hardware
           |
           --- esp8266com
               |
               --- esp8266
                   |
                   --- bootloaders
                   --- cores
                   --- doc
                   --- libraries
                   --- package
                   --- tests
                   --- tools
                   --- variants
                   --- platform.txt
                   --- programmers.txt
                   --- README.md
                   --- boards.txt
                   --- LICENSE


 
__Initialize the submodules__

   .. code:: bash

       cd esp8266
       git submodule update --init   
  
  If error messages about missing files related to ``SoftwareSerial`` are encountered during the build process, it should be because this step was missed and is required.

__Download binary tools__

   .. code:: bash

       cd esp8266/tools
       python get.py

- Restart Arduino

    
