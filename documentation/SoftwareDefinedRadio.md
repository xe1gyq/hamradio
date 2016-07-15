# Software Defined Radio

# PreRequisites

    xe1gyq@jessie:~$ su
    Password: 
    root@jessie:/home/xe1gyq# apt-get update
    root@jessie:/home/xe1gyq# apt-get install gnuradio gnuradio-dev
    root@jessie:/home/xe1gyq# apt-get install rtl-sdr gr-osmosdr
    root@jessie:/home/xe1gyq# apt-get install cmake libboost-dev sqlite pyqt4-dev-tools liblog4cpp5-dev swig
    
# RTL2838UHIDIR

    root@jessie:/home/xe1gyq# dmesg
    [11699.984048] usb 5-3: new high-speed USB device number 20 using ehci-pci
    [11700.127894] usb 5-3: New USB device found, idVendor=0bda, idProduct=2838
    [11700.127898] usb 5-3: New USB device strings: Mfr=1, Product=2, SerialNumber=3
    [11700.127901] usb 5-3: Product: RTL2838UHIDIR
    [11700.127903] usb 5-3: Manufacturer: Realtek
    [11700.127906] usb 5-3: SerialNumber: 00000001
    root@jessie:/home/xe1gyq# lsusb
    Bus 005 Device 020: ID 0bda:2838 Realtek Semiconductor Corp. RTL2838 DVB-T

