---
layout: post
title:  Arreglar disco duro/pendrive (badblocks)
date:   2019-08-07 23:42:14 -0300
categories: Debian
---
A veces un disco duro tiene sectores defectuosos. Con lo siguiente consigo que en el índice del disco duro se añadan los sectores defectuosos y así el disco duro vuelve a ser funcional.

`badblocks -wvsb 4096 /dev/sdb`

[::fuente::](https://es.wikipedia.org/wiki/Badblocks)

Esto escribe 4 patrones diferentes en todo el disco "/dev/sdb", y lo verifica leyéndolo de nuevo.

`# badblocks -wsv -t random /dev/device`

[::fuente::](https://wiki.archlinux.org/index.php/Badblocks_(Español))

Esto escribe 1 patrón aleatorio en el disco "/dev/sdb", y lo verifica leyéndolo de nuevo. Este método hace una sola pasada mientras que el anterior hacía cuatro pasadas. Lo he probado con un disco duro que daba errores (de un portátil) y lo he recuperado.
Eso si las cuatro pasadas tardan mucho y si el disco es grande mucho más. Si quieres que tarde menos hazlo con una pasada. 