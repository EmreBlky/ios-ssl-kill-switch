iOS SSL Kill Switch
===================

Blackbox tool to disable SSL certificate validation - including certificate
pinning - within iOS Apps

Description
-----------

Once installed on a jailbroken device, iOS SSL Kill Switch patches
NSURLConnection to override and disable the system's default
certificate validation as well as any kind of custom certificate
validation (such as certificate pinning). It was succesfully tested
against Twitter, Card.io and Square; all of them implement
certificate pinning.


Installation
------------

Most users should download the pre-compiled Debian package available at:
https://www.dropbox.com/sh/5bbfvf3ux713gn2/JV7Ul6Goyj

### Dependencies

iOS SSL Kill Switch was tested on iOS 4.3 or 5.1. A jailbroken device
is required. Using Cydia make sure the following packages are installed:
- dpkg
- MobileSubstrate
- PreferenceLoader

### How to install

Download and copy the Debian package to the device; install it:  

    dpkg -i <package>.deb

Respring the device:

    killall -HUP SpringBoard

There should be a new menu in the device's Settings where you can
enable the extension.

Finally, start / restart the App you want to test.

### How to uninstall

    dpkg -r com.isecpartners.nabla.sslkillswitch


Build
-----

Most users should just download and install the Debian package.
The build requires the Theos suite to be installed; 
see http://www.iphonedevwiki.net/index.php/Theos/Getting_Started .
You first have to create a symlink to your theos installation:

    ln -s /opt/theos/ theos

Then, the package can be built using:

    make package


License
-------

MIT - See LICENSE.txt


Author
------

Alban Diquet - https://github.com/nabla-c0d3
