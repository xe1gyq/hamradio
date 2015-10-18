# Projects

## Cancun v0.1, Voice Experimental Station

## Huatulco v2.0, Low Power Station 

- MinnowBoard Max http://www.minnowboard.org/meet-minnowboard-max/
- SSD ADATA 32 GB
- Debian Wheezy
- Debian Jessie
- SSH Server
- Standard System Utilities

### APRS

Automatic Packet Reporting System (APRS™)
- http://aprs.org/
- http://info.aprs.net/
- http://aprs.fi
Xastir
- http://xastir.org/ 
- http://www.linuxjournal.com/article/10621

Graphical User Interface Installation

    root@Minnowboard:~# apt-get install task-lxde-desktop

Xastir Installation
Hasta la puiblicacion de esta seccion no se encontro candidato de Xastir para instalacion con apt-get, esta es la opcion de compilar el codigo fuente
 
root@Minnowboard:~# apt-get install libx11-dev lesstif2-dev
<cambio a tu usuario>
root@Minnowboard:~$ wget <url del codigo fuente de xastir en formato tar.gz>
root@Minnowboard:~$ tar zxvf xastir-2.0.6.tar.gz
root@Minnowboard:~$ cd xastir-2.0.6
root@Minnowboard:~$ ./configure
root@Minnowboard:~$ make
<cambio a root>
root@Minnowboard:~# make install

Iniciando Xastir
root@Minnowboard:~$ xastir &

Configurando Xastir | Estacion & Acceso a Internet
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


