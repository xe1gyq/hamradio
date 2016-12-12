# HackRF

- [Smart Sniffing GSM Traffic on Windows Workstation and VMWare with HackRF and RTL SDR](http://www.instructables.com/id/SMART-SNIFFING-GSM-TRAFFIC-ON-WINDOWS-WORKSTATION-/?ALLSTEPS)
- [Getting Started with HackRF and GNU Radio](https://github.com/mossmann/hackrf/wiki/Getting-Started-with-HackRF-and-GNU-Radio)

```sh
root@jessie:~$ git clone https://github.com/scateu/kalibrate-hackrf.git
```

```sh
root@jessie:~# dmesg
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
root@jessie:~# 
```

```sh
root@jessie:~# lsusb
Bus 004 Device 002: ID 8087:8000 Intel Corp. 
Bus 004 Device 001: ID 1d6b:0002 Linux Foundation 2.0 root hub
Bus 003 Device 002: ID 8087:8008 Intel Corp. 
Bus 003 Device 001: ID 1d6b:0002 Linux Foundation 2.0 root hub
Bus 002 Device 001: ID 1d6b:0003 Linux Foundation 3.0 root hub
Bus 001 Device 004: ID 1d50:6089 OpenMoko, Inc. 
Bus 001 Device 003: ID 04f2:b39a Chicony Electronics Co., Ltd 
Bus 001 Device 002: ID 8087:07dc Intel Corp. 
Bus 001 Device 001: ID 1d6b:0002 Linux Foundation 2.0 root hub
root@jessie:~# 
```

```sh
root@jessie:~# nano /etc/udev/rules.d/52-hackrf.rules
```

```sh
ATTR{idVendor}=="1d50", ATTR{idProduct}=="604b", SYMLINK+="hackrf-jawbreaker-%k", MODE="660", GROUP="plugdev"
ATTR{idVendor}=="1d50", ATTR{idProduct}=="6089", SYMLINK+="hackrf-one-%k", MODE="660", GROUP="plugdev"
ATTR{idVendor}=="1fc9", ATTR{idProduct}=="000c", SYMLINK+="hackrf-dfu-%k", MODE="660", GROUP="plugdev"
```

```
root@jessie:~# udevadm control --reload-rules
root@jessie:~# 
```

```sh
root@jessie:~# lsmod | grep hackrf
hackrf                 28672  0 
videobuf2_vmalloc      16384  2 uvcvideo,hackrf
videobuf2_core         49152  2 uvcvideo,hackrf
v4l2_common            16384  2 hackrf,videobuf2_core
videodev              172032  4 uvcvideo,hackrf,v4l2_common,videobuf2_core
root@jessie:~# 
```

```sh
user@jessie:~$ mkdir ~/sdr
user@jessie:~$ cd sdr/
user@jessie:~/sdr$ git clone https://github.com/mossmann/hackrf.git
Clonar en «hackrf»...
remote: Counting objects: 10714, done.
remote: Compressing objects: 100% (5/5), done.
remote: Total 10714 (delta 0), reused 0 (delta 0), pack-reused 10709
Receiving objects: 100% (10714/10714), 33.69 MiB | 1.11 MiB/s, done.
Resolving deltas: 100% (7622/7622), done.
Comprobando la conectividad… hecho.
pymelab@workstation:~/sdr$ cd hackrf/host
pymelab@workstation:~/sdr/hackrf/host$ mkdir build && cd build
pymelab@workstation:~/sdr/hackrf/host/build$ 

```


```sh
root@jessie:~$ rtl_test -t
```