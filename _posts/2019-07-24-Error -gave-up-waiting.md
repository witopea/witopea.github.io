---
layout: post
title:  Error gave up waiting for suspend/resume device
date:   2019-07-24 21:32:14 -0300
categories: Debian
---
Tras instalar varias instancias de Debian 10 en mi equipo que compartían la partición Swap
me empezó a salir al iniciar el equipo el mensaje de alerta del título.

Tras investigar [aquí](http://forums.debian.net/viewtopic.php?f=5&t=138796) di con la tecla.

Me fui al directorio: `/etc/initramfs-tools/conf.d/` allí encontré el archivo resume y dentro del mismo
`RESUME=UUID=a5a798bb-dea4-4638-915a-8f51a549f79e` que hacía referencia al UUID de mi partición swap pero era incorrecto.
Al instalar Debian y usar la misma partición Swap que en otras instalaciones del equipo, este UUID irremediablente.

Cambié en ese archivo el UUID por el de mi partición swap. Para ello puedes abrir la aplicación gráfica gparted y mirar
la información de la partición swap donde vienen la UUID o buscarla en la salida del comando `# blkid`

Después de eso hice un `# update-initramfs -u`.

Tambien tienes que cambiar el UUID en el archivo `/etc/fstab` y solucionado.
