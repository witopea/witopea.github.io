---
layout: post
title:  rsync desde ordenador a móvil
date:   2019-08-06 15:33:14 -0300
categories: Debian
---

En el móvil instalo la aplicación sshelper disponible en el playstore.
Inicio la aplicación en el móvil y compruebo desde la aplicación cual es la ip y el puerto (normalmente 2222).
Con esto desde el ordenador que está conectado a la misma red Wifi realizo el siguiente comando:

`rsync --exclude ".thumb*" --remove-source-files -avzHPe "ssh -p2222" root@192.168.1.245:/sdcard/DCIM/ ./`

La segunda opción es para tomar dos directorios de la carpeta DCMI, el directorio Camera y el OpenCamera (de una
aplicación que uso)

`rsync --include 'Camera/***' --include 'OpenCamera/***' --exclude "*" --remove-source-files -avzHPe "ssh -p2222" root@192.168.1.236:/sdcard/DCIM/ ./`

Puedes usar la opción `--delete` para eliminar los datos locales que no estén en origen, úsalo con precaución. Te pedirá
la contraseña que previamente has puesto en la aplicación del móvil y empezará a realizar la sincronización.
Verdaderamente genial.

---
Este tip está tal como lo redacté para mi. Lo modificaré para que sea más general. 
