# GNU Radio Companion

## Empty

```sh
root@jessie:~# gnuradio-companion 
linux; GNU C++ version 4.9.1; Boost_105500; UHD_003.007.003-0-unknown

<<< Welcome to GNU Radio Companion 3.7.5 >>>

Preferences file: /root/.grc
Block paths:
	/usr/share/gnuradio/grc/blocks
	/root/.grc_gnuradio

Loading: "/root/untitled.grc"
>>> Done

Showing: "/root/untitled.grc"
root@jessie:~# 
```

## Xe1Gyq Sdr Git Repository

```sh
root@jessie:~# git clone https://github.com/xe1gyq/sdr.git
Cloning into 'sdr'...
remote: Counting objects: 19, done.
remote: Total 19 (delta 0), reused 0 (delta 0), pack-reused 19
Unpacking objects: 100% (19/19), done.
Checking connectivity... done.
root@jessie:~# cd sdr
root@jessie:~/sdr# ls
01  02	LICENSE
root@jessie:~/sdr# 
```

```sh
root@jessie:~/sdr# ls
01  02	LICENSE
root@jessie:~/sdr# cd 01/
root@jessie:~/sdr/01# ls
01.grc	top_block.py
root@jessie:~/sdr/01# 
```

```sh
root@jessie:~/sdr/01# gnuradio-companion 01.grc
linux; GNU C++ version 4.9.1; Boost_105500; UHD_003.007.003-0-unknown

<<< Welcome to GNU Radio Companion 3.7.5 >>>

Preferences file: /root/.grc
Block paths:
	/usr/share/gnuradio/grc/blocks
	/root/.grc_gnuradio

Loading: "01.grc"
>>> Done

Showing: "/root/sdr/01/01.grc"
root@jessie:~/sdr/01# 
```

```sh
root@jessie:~/sdr/01# python top_block.py 
Using Volk machine: ssse3_32_orc
```