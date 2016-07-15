# Setup

# Packages

```sh
xe1gyq@jessie:~$ sudo su
Password: 
root@jessie:/home/xe1gyq# cd
root@jessie:~# apt-get update
root@jessie:~# apt-get install gnuradio gnuradio-dev
root@jessie:~# apt-get install rtl-sdr gr-osmosdr
root@jessie:~# apt-get install gqrx-sdr
root@jessie:~# apt-get install cmake libboost-dev sqlite pyqt4-dev-tools liblog4cpp5-dev swig
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