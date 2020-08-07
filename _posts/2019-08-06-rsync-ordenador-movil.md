---
layout: post
title:  rsync desde ordenador a móvil o viceversa
date:   2019-08-06 15:33:14 -0300
categories: Debian
---
![](/images/pinguinos.jpg) { width=50% }
rsync es fantástico. Una utilidad que le doy es para sincronizar carpetas de mi ordenador a mi móvil sin ningún intermediario por medio. Te explico como lo hago.

## ¿Qué necesitamos?

1. rsync (probablemente lo tengas ya instalado en tu distribución de linux)
2. SSHelpler en tu móvil Android. Antes lo instalaba desde el PlayStore, pero las nuevas versiones han dejado de ser compatible con Android 6 y he tenido que bajar una versión antigua de SSHelper. He elegido la versión 11.9. Puedes descargarla de [aquí](https://arachnoid.com/android/SSHelper/APK_release_archive/)

## Haciéndolo funcionar...

Inicia SSHelper en el móvil y comprueba desde la aplicación cual es la ip del móvil (supongamos que es 192.168.1.15) y el puerto (normalmente 2222).

Ahora desde el ordenador que está conectado a la misma red Wifi ejecutas en el terminal los comandos de rsync que quieras para pasar archivos y carpetas de un lugar a otro.

Te pedirá la contraseña que previamente has puesto en la aplicación del móvil o (admin sin no la has cambiado) y empezará a realizar la sincronización.

## Ejemplo1 : Pasar fotos del móvil al ordenador y eliminarlas del móvil.

`rsync --exclude ".thumb*" --remove-source-files -avzHPe "ssh -p2222" root@192.168.1.15:/sdcard/DCIM/ /home/usuario/fotos`

## Ejemplo2 : Pasar una carpeta del ordenador al móvil.

`rsync --delete-after -rlgoe "ssh -p2222" /home/usuario/MarkDown/ root@192.168.1.15:/sdcard/MarkDown`

Para ver todas las opciones de rsync, `man rsync`, o visita [esta página](https://linux.die.net/man/1/rsync)
-r (recursive)
-l ()
-g (group)
-o (owner)
-e (specify the remote shell to use)
**Nota:** Puedes usar la opción `--delete-after` para eliminar en el destino todo lo que no esté en origen.

## Mi comentario.
He visto otras opciones como syncthing, pero me gusta más esta opción por su sencillez. Tan sólo tengo que abrir SSHelper cuando quiero sincronizar con el móvil y ejecutar un pequeño script. Obviamente se puede personalizar a las necesidades de cada uno. Lo puedes poner en el cron, etc... Con syncthing siempre tenía que tener esta aplicación en el móvil de fondo y no me gustaba eso, siempre consumiendo recursos innecesariamente en mi caso, SSHelper lo enciendo y apago cuando quiero.