iOS SSL Kill Switch
===================


MobileSubstrate extension to disable certificate validation at run-time in order 
to facilitate black-box testing of iOS Apps. 

https://github.com/nabla-c0d3/ios-ssl-kill-switch


How it works
------------

Once installed, iOS SSL Kill Switch patches NSURLConnection to override and disable the system's default certificate validation as well as any kind of custom certificate validation (such as certificate pinning).


Installation
------------

iOS SSL Kill Switch was tested on iOS 4.3 or 5.1.

### Dependencies

Using Cydia make sure the following packages are installed:
- dpkg
- MobileSubstrate
- PreferenceLoader

### How to install

Copy the Debian package to the device and install it:  

    dpkg -i <package>.deb

Respring the device:

    killall -HUP SpringBoard

There should be a new menu in the device's Settings where you can enable the extension.

Finally, start / restart the App you want to test.

### How to uninstall

    dpkg -r com.nabla.sslkillswitch


TODO
----

- Disable certificate validation for NSStream and CFStream
- Force NSStream and CFStream to use the device's proxy settings


License
-------

MIT - See LICENSE.txt

Copyright 2012 Alban Diquet