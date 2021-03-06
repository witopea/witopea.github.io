---
layout: post
title:  Arreglar disco duro/pendrive (badblocks)
date:   2019-08-07 23:42:14 -0300
categories: Debian
---
A veces un disco duro tiene sectores defectuosos. Con lo siguiente consigo que en el índice del disco duro se añadan
 los sectores defectuosos y así el disco duro vuelve a ser funcional.
 
La siguiente instrucción escribe 4 patrones diferentes en todo el disco "/dev/sdb", y lo verifica leyéndolo de nuevo.

`badblocks -wvsb 4096 /dev/sdb`

[::fuente::
](https://es.wikipedia.org/wiki/Badblocks)

La siguiente es más rápida porque hace una sola pasada escribiendo un patrón aleatorio en el disco "/dev/sdb", y después lo verifica leyéndolo de nuevo. 

`# badblocks -wsv -t random /dev/device`

[::fuente::
](https://wiki.archlinux.org/index.php/Badblocks_(Español))

La primera opción (las cuatro pasadas) tarda mucho y si el disco es grande mucho más. La segunda opción (sólo una pasada) tarda mucho menos.
Si no tienes instalada el programa badblocks, tienes que instalar el paquete **e2fsprogs**

`# apt install e2fsprogs`