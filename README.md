raspbian-wifi-config-from-usb
=============================

This is a utility that configures a Raspberry Pi's WiFi settings based on a
configuration file on a USB stick.

Instructions
=============================

On your Raspberry Pi (running Raspbian):

    sudo apt-get install usbmount

    git clone https://github.com/canopy-project/raspbian-wifi-config-from-usb.git
    cd raspbian-wifi-config-from-usb
    make
    sudo make install

To enable it, add the following line to /etc/rc.local

    /usr/local/bin/raspbian-wifi-config-from-usb &


Behaviour
=============================

This program will continuously monitor the connected USB drives for a file
called `canopy-wifi.conf` in the USB drive's top-level driectory.  If such a
file is found, its settings will be read and applied.


canopy-wifi.conf Format
=============================
`canopy-wifi.conf` is a simple 2-line file with the following format:

    SSID
    PASSWORD
