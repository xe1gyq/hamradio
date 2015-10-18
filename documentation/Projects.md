# Projects

## Cancun v0.1, Voice Experimental Station

## Huatulco v2.0, Low Power Station 

- MinnowBoard Max http://www.minnowboard.org/meet-minnowboard-max/
- SSD ADATA 32 GB
- Debian Wheezy
- Debian Jessie
- SSH Server
- Standard System Utilities

### Automatic Packet Reporting System (APRS™) via Xastir

APRS
- http://aprs.org/
- http://info.aprs.net/
- http://aprs.fi

Xastir
- http://xastir.org/ 
- http://www.linuxjournal.com/article/10621

#### Graphical User Interface Installation

    root@Minnowboard:~# apt-get install task-lxde-desktop

#### Xastir Installation

No apt-get candidate for Debian Whezzy so manual compilation required

    root@Minnowboard:~# apt-get install libx11-dev lesstif2-dev
    user@Minnowboard:~$ wget <xastir source code tar.gz>
    user@Minnowboard:~$ tar zxvf xastir-2.0.6.tar.gz
    user@Minnowboard:~$ cd xastir-2.0.6
    user@Minnowboard:~$ ./configure
    user@Minnowboard:~$ make
    root@Minnowboard:~# make install
    user@Minnowboard:~$ xastir &

Xastir Configuration Station & Internet Access

    @Xastir> File -> Configure -> Station
     Callsign
     LAT
     LONG
     Station Symbol
     Power - Height (HAAT) - Gain - Directivity
     Comment

    @Xastir> Interface -> Interface Control -> Add -> Internet Server
     Host
     Port
     Pass-code

     @Xastir> Interface -> Interface Control -> Seleccionar "Device 0 Internet Server" -> Start


