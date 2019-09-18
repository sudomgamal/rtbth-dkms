This is a Linux kernel module for a Ralink RT3290 wireless device.
It enables [Bluez](http://www.bluez.org) software and driver support for RT3290.

This module has no official support by Mediatek. Support was discontinued.


### Usage: ###

```sh
# Init
sudo modprobe rtbth
sudo rfkill unblock bluetooth
hcitool dev # check

# Switch off
sudo rfkill block bluetooth

# Switch on
sudo rfkill unblock bluetooth

# Shutdown
sudo pkill -2 rtbt
sudo rmmod rtbth
```


### Installation: ###

[Ubuntu and derivatives](https://launchpad.net/~blaze/+archive/ubuntu/rtbth-dkms)

## Manual build/install for openSuse  

``` sh
#install requireed packages:
sudo zypper install kernel-devel dkms

#copy the source folder to /usr/src/ to be visible to dkms
sudo cp -rf ./rtbth-dkms /usr/src/

#build and install the module using dkms
sudo dkms add -m rtbth/dkms
sudo dkms build -m rtbth/dkms
sudo dkms install -m rtbth/dkms

#load the module
sudo modprobe rtbth
sudo rfkill unblock bluetooth
hcitool dev # check
```
