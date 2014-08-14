raspbian-wifi-config-from-usb
=============================

This is a utility that configures a Raspberry Pi's WiFi settings based on a
configuration file on a USB stick.

Instructions
=============================

Follow these instructions on your Raspberry Pi that is running Raspbian.

It is recommended to first backup your existing network configuration.

    sudo cp /etc/network/interfaces /etc/network/interfaces.backup

This utility requires USB drive automounting:

    sudo apt-get install usbmount

Now build and install the program:

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
