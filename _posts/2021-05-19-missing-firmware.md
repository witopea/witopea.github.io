---
layout: post
title:  Missing firmware
date:   2021-05-19 10:10:32
categories: Debian
---
A veces al instalar debian te sale un mensaje de *missing firmware*. Instalas, los paquetes necesarios y sigues obteniendo dicho error.
En  [esta página por ejemplo](http://forums.debian.net/viewtopic.php?f=30&t=145496) he visto como se puede solventar el problema.

> $ sudo -i
> # cd /lib/firmware/rtl_nic
> # wget https://git.kernel.org/pub/scm/linux/kernel/git/firmware/linux-firmware.git/plain/rtl_nic/rtl8125a-3.fw
> # update-initramfs -u

Eso es todo :)