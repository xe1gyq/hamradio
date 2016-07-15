# Setup

# Packages 

## Core

```sh
xe1gyq@jessie:~$ sudo su
Password: 
root@jessie:/home/xe1gyq# cd
root@jessie:~# apt-get update
root@jessie:~# apt-get install gnuradio gnuradio-dev
root@jessie:~# apt-get install gqrx-sdr
root@jessie:~# apt-get install gr-osmosdr
root@jessie:~# apt-get install cmake libboost-dev sqlite pyqt4-dev-tools liblog4cpp5-dev swig
```

## Common SDR Dongles

```sh
root@jessie:~# apt-get install rtl-sdr hackrf bladerf-host gr-fcdproplus qthid-fcd-controller
```

## Python

```sh
root@jessie:~# pip install pyrtlsdr
Collecting pyrtlsdr
  Downloading pyrtlsdr-0.2.3-py2.py3-none-any.whl
Installing collected packages: pyrtlsdr
Successfully installed pyrtlsdr-0.2.3
You are using pip version 8.1.1, however version 8.1.2 is available.
You should consider upgrading via the 'pip install --upgrade pip' command.
root@jessie:~# 
```

# Manual

```sh
root@jessie:~$ git clone --recursive git://git.gnuradio.org/gnuradio.git
root@jessie:~$ cd gnuradio
root@jessie:~$ mkdir build
root@jessie:~$ cd build
root@jessie:~$ cmake ../
root@jessie:~$ make
root@jessie:~$ make test
root@jessie:~# make install
```