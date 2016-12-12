# HackRF

- [Smart Sniffing GSM Traffic on Windows Workstation and VMWare with HackRF and RTL SDR](http://www.instructables.com/id/SMART-SNIFFING-GSM-TRAFFIC-ON-WINDOWS-WORKSTATION-/?ALLSTEPS)
- [Getting Started with HackRF and GNU Radio](https://github.com/mossmann/hackrf/wiki/Getting-Started-with-HackRF-and-GNU-Radio)

```sh
root@jessie:~$ git clone https://github.com/scateu/kalibrate-hackrf.git
```

```sh
root@jessie:~$ dmesg
...
[  788.810938] usb 1-3: new high-speed USB device number 4 using xhci_hcd
[  788.940251] usb 1-3: New USB device found, idVendor=1d50, idProduct=6089
[  788.940260] usb 1-3: New USB device strings: Mfr=1, Product=2, SerialNumber=0
[  788.940265] usb 1-3: Product: HackRF One
[  788.940268] usb 1-3: Manufacturer: Great Scott Gadgets
[  788.984347] hackrf 1-3:1.0: Board ID: 02
[  788.984351] hackrf 1-3:1.0: Firmware version: 2014.08.1
[  788.984585] hackrf 1-3:1.0: Registered as swradio0
[  788.984587] hackrf 1-3:1.0: SDR API is still slightly experimental and functionality changes may follow
[  788.984606] usbcore: registered new interface driver hackrf
root@jessie:~$ 
```

```sh
pymelab@workstation:~$ lsusb
Bus 004 Device 002: ID 8087:8000 Intel Corp. 
Bus 004 Device 001: ID 1d6b:0002 Linux Foundation 2.0 root hub
Bus 003 Device 002: ID 8087:8008 Intel Corp. 
Bus 003 Device 001: ID 1d6b:0002 Linux Foundation 2.0 root hub
Bus 002 Device 001: ID 1d6b:0003 Linux Foundation 3.0 root hub
Bus 001 Device 004: ID 1d50:6089 OpenMoko, Inc. 
Bus 001 Device 003: ID 04f2:b39a Chicony Electronics Co., Ltd 
Bus 001 Device 002: ID 8087:07dc Intel Corp. 
Bus 001 Device 001: ID 1d6b:0002 Linux Foundation 2.0 root hub
pymelab@workstation:~$ 
```

```sh
```