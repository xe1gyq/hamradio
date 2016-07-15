# RTL2838UHIDIR

```sh
root@jessie:~# dmesg
[11699.984048] usb 5-3: new high-speed USB device number 20 using ehci-pci
[11700.127894] usb 5-3: New USB device found, idVendor=0bda, idProduct=2838
[11700.127898] usb 5-3: New USB device strings: Mfr=1, Product=2, SerialNumber=3
[11700.127901] usb 5-3: Product: RTL2838UHIDIR
[11700.127903] usb 5-3: Manufacturer: Realtek
[11700.127906] usb 5-3: SerialNumber: 00000001
root@jessie:~# lsusb
Bus 005 Device 020: ID 0bda:2838 Realtek Semiconductor Corp. RTL2838 DVB-T
```

```sh
root@jessie:~# lsusb
Bus 003 Device 002: ID 046d:c31c Logitech, Inc. Keyboard K120 for Business
Bus 003 Device 003: ID 046d:c05a Logitech, Inc. M90/M100 Optical Mouse
Bus 005 Device 002: ID 0403:6001 Future Technology Devices International, Ltd FT232 USB-Serial (UART) IC
Bus 006 Device 002: ID 148f:5370 Ralink Technology, Corp. RT5370 Wireless Adapter
Bus 007 Device 005: ID 0bda:2838 Realtek Semiconductor Corp. RTL2838 DVB-T
Bus 001 Device 001: ID 1d6b:0001 Linux Foundation 1.1 root hub
Bus 002 Device 001: ID 1d6b:0001 Linux Foundation 1.1 root hub
Bus 003 Device 001: ID 1d6b:0001 Linux Foundation 1.1 root hub
Bus 004 Device 001: ID 1d6b:0001 Linux Foundation 1.1 root hub
Bus 005 Device 001: ID 1d6b:0001 Linux Foundation 1.1 root hub
Bus 006 Device 001: ID 1d6b:0002 Linux Foundation 2.0 root hub
Bus 007 Device 001: ID 1d6b:0002 Linux Foundation 2.0 root hub
root@jessie:~# 
```

```sh
root@jessie:~# 
root@jessie:~# 
```

```sh
root@jessie:~# rtl_test -t
Found 1 device(s):
  0:  Realtek, RTL2838UHIDIR, SN: 00000001

Using device 0: Generic RTL2832U OEM
Found Rafael Micro R820T tuner
Supported gain values (29): 0.0 0.9 1.4 2.7 3.7 7.7 8.7 12.5 14.4 15.7 16.6 19.7 20.7 22.9 25.4 28.0 29.7 32.8 33.8 36.4 37.2 38.6 40.2 42.1 43.4 43.9 44.5 48.0 49.6 
Sampling at 2048000 S/s.
No E4000 tuner found, aborting.
root@jessie:~# 
```

```sh
root@jessie:~# rtl_fm -f 96.3e6 -M wbfm -s 200000 -r 48000 - | aplay -r 48k -f S16_LE
Found 1 device(s):
  0:  Realtek, RTL2838UHIDIR, SN: 00000001

Using device 0: Generic RTL2832U OEM
Found Rafael Micro R820T tuner
Tuner gain set to automatic.
Tuned to 96616000 Hz.
Oversampling input by: 6x.
Oversampling output by: 1x.
Buffer size: 6.83ms
Sampling at 1200000 S/s.
Output at 200000 Hz.
Playing raw data 'stdin' : Signed 16 bit Little Endian, Rate 48000 Hz, Mono
underrun!!! (at least 327.050 ms long)

```
