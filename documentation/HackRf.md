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
pymelab@workstation:~/sdr/hackrf/host/build$ cmake ../ -DINSTALL_UDEV_RULES=ON
-- The C compiler identification is GNU 4.8.4
-- The CXX compiler identification is GNU 4.8.4
-- Check for working C compiler: /usr/bin/cc
-- Check for working C compiler: /usr/bin/cc -- works
-- Detecting C compiler ABI info
-- Detecting C compiler ABI info - done
-- Check for working CXX compiler: /usr/bin/c++
-- Check for working CXX compiler: /usr/bin/c++ -- works
-- Detecting CXX compiler ABI info
-- Detecting CXX compiler ABI info - done
-- Check if the system is big endian
-- Searching 16 bit integer
-- Looking for sys/types.h
-- Looking for sys/types.h - found
-- Looking for stdint.h
-- Looking for stdint.h - found
-- Looking for stddef.h
-- Looking for stddef.h - found
-- Check size of unsigned short
-- Check size of unsigned short - done
-- Using unsigned short
-- Check if the system is big endian - little endian
-- Found PkgConfig: /usr/bin/pkg-config (found version "0.26") 
-- checking for module 'libusb-1.0'
--   found libusb-1.0, version 1.0.17
-- Found LIBUSB: /usr/lib/x86_64-linux-gnu/libusb-1.0.so  
-- Looking for include file pthread.h
-- Looking for include file pthread.h - found
-- Looking for pthread_create in pthreads
-- Looking for pthread_create in pthreads - not found
-- Looking for pthread_create in pthread
-- Looking for pthread_create in pthread - found
-- Found Threads: TRUE  
-- Setting udev rule group to - plugdev
-- HackRF udev rules will be installed to '/etc/udev/rules.d' upon running 'make install'
-- Configuring done
-- Generating done
-- Build files have been written to: /home/pymelab/sdr/hackrf/host/build
pymelab@workstation:~/sdr/hackrf/host/build$ 
```

```sh
pymelab@workstation:~/sdr/hackrf/host/build$ make
Scanning dependencies of target hackrf
[ 11%] Building C object libhackrf/src/CMakeFiles/hackrf.dir/hackrf.c.o
Linking C shared library libhackrf.so
[ 11%] Built target hackrf
Scanning dependencies of target hackrf-static
[ 22%] Building C object libhackrf/src/CMakeFiles/hackrf-static.dir/hackrf.c.o
Linking C static library libhackrf.a
[ 22%] Built target hackrf-static
Scanning dependencies of target hackrf_cpldjtag
[ 33%] Building C object hackrf-tools/src/CMakeFiles/hackrf_cpldjtag.dir/hackrf_cpldjtag.c.o
Linking C executable hackrf_cpldjtag
[ 33%] Built target hackrf_cpldjtag
Scanning dependencies of target hackrf_info
[ 44%] Building C object hackrf-tools/src/CMakeFiles/hackrf_info.dir/hackrf_info.c.o
Linking C executable hackrf_info
[ 44%] Built target hackrf_info
Scanning dependencies of target hackrf_max2837
[ 55%] Building C object hackrf-tools/src/CMakeFiles/hackrf_max2837.dir/hackrf_max2837.c.o
Linking C executable hackrf_max2837
[ 55%] Built target hackrf_max2837
Scanning dependencies of target hackrf_rffc5071
[ 66%] Building C object hackrf-tools/src/CMakeFiles/hackrf_rffc5071.dir/hackrf_rffc5071.c.o
Linking C executable hackrf_rffc5071
[ 66%] Built target hackrf_rffc5071
Scanning dependencies of target hackrf_si5351c
[ 77%] Building C object hackrf-tools/src/CMakeFiles/hackrf_si5351c.dir/hackrf_si5351c.c.o
Linking C executable hackrf_si5351c
[ 77%] Built target hackrf_si5351c
Scanning dependencies of target hackrf_spiflash
[ 88%] Building C object hackrf-tools/src/CMakeFiles/hackrf_spiflash.dir/hackrf_spiflash.c.o
Linking C executable hackrf_spiflash
[ 88%] Built target hackrf_spiflash
Scanning dependencies of target hackrf_transfer
[100%] Building C object hackrf-tools/src/CMakeFiles/hackrf_transfer.dir/hackrf_transfer.c.o
Linking C executable hackrf_transfer
[100%] Built target hackrf_transfer
```

```sh
pymelab@workstation:~/sdr/hackrf/host/build$ sudo make install
sudo: imposible resolver el anfitrión workstation
[ 11%] Built target hackrf
[ 22%] Built target hackrf-static
[ 33%] Built target hackrf_cpldjtag
[ 44%] Built target hackrf_info
[ 55%] Built target hackrf_max2837
[ 66%] Built target hackrf_rffc5071
[ 77%] Built target hackrf_si5351c
[ 88%] Built target hackrf_spiflash
[100%] Built target hackrf_transfer
Install the project...
-- Install configuration: ""
-- Installing: /usr/local/lib/pkgconfig/libhackrf.pc
-- Installing: /etc/udev/rules.d/53-hackrf.rules
-- Installing: /usr/local/lib/libhackrf.so.0.4.0
-- Installing: /usr/local/lib/libhackrf.so.0
-- Installing: /usr/local/lib/libhackrf.so
-- Installing: /usr/local/lib/libhackrf.a
-- Installing: /usr/local/include/libhackrf/hackrf.h
-- Installing: /usr/local/bin/hackrf_max2837
-- Removed runtime path from "/usr/local/bin/hackrf_max2837"
-- Installing: /usr/local/bin/hackrf_si5351c
-- Removed runtime path from "/usr/local/bin/hackrf_si5351c"
-- Installing: /usr/local/bin/hackrf_transfer
-- Removed runtime path from "/usr/local/bin/hackrf_transfer"
-- Installing: /usr/local/bin/hackrf_rffc5071
-- Removed runtime path from "/usr/local/bin/hackrf_rffc5071"
-- Installing: /usr/local/bin/hackrf_spiflash
-- Removed runtime path from "/usr/local/bin/hackrf_spiflash"
-- Installing: /usr/local/bin/hackrf_cpldjtag
-- Removed runtime path from "/usr/local/bin/hackrf_cpldjtag"
-- Installing: /usr/local/bin/hackrf_info
-- Removed runtime path from "/usr/local/bin/hackrf_info"
pymelab@workstation:~/sdr/hackrf/host/build$ 
```

```sh
pymelab@workstation:~/sdr/hackrf/host/build$ sudo ldconfig
```

```sh
pymelab@workstation:~/sdr/hackrf/host/build$ hackrf_info
Found HackRF board.
Board ID Number: 2 (HackRF One)
Firmware Version: 2014.08.1
Part ID Number: 0xa000cb3c 0x006d4749
Serial Number: 0x00000000 0x00000000 0x321864c8 0x3952811d
pymelab@workstation:~/sdr/hackrf/host/build$ 
```

```sh
root@jessie:~$ rtl_test -t
```

```sh
root@jessie:~$ ./gqrx
```
- [](https://mborgerson.com/getting-started-with-the-hackrf-one-on-ubuntu-14-04)
- [](http://gqrx.dk/doc/practical-tricks-and-tips_
