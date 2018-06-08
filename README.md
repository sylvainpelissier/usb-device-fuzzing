usb-device-fuzzing
==================

Some tools for testing USB devices with Python 3

This code was first released at T2 Infosec 2012: http://www.t2.fi/2012/

simple_ctrl_fuzzer.py: simple fuzzer for USB control transfers

USBFuzz: python modules for building USB fuzzers

USBFuzz.Exceptions: common exception definitions for the USBFuzz modules

USBFuzz.Device: module to interface with USB devices

USBFuzz.MSC: scapy layers and USB device interface class for the USB Bulk-Only Mass Storage Class

USBFuzz.SCSI: scapy layers for SCSI primary and bulk commands, used by USBFuzz.MSC

USBFuzz.CCID: scapy layers and USB device interface class for the USB Integrated Circuit Cards Interface Device Class

USBFuzz.MTP: scapy layers and USB device interface class for the USB Media Tranfer Protocol (based on Picture Transfer Protocol)

USBFuzz.QCDM: scapy layers and USB device interface class for the Qualcomm baseband DIAG protocol

examples: examples of simple fuzzers built using the USBFuzz modules

## Install

To work properly the fuzzers needs the packages: python3-usb and python3-scapy

If you cannot run the fuzzer within a user account you have to create a udev rule:
```
sudo nano /etc/udev/rules.d/99-usb-device.rules 
```
with contents:
```
SUBSYSTEM=="usb", ATTR{idVendor}=="<idVendor>", ATTR{idProduct}=="<idProduct>", MODE="666"
```

## Example

Start the simple fuzzer with the command:
```
./simple_ctrl_fuzzer.py <idVendor>:<idProduct>
```
