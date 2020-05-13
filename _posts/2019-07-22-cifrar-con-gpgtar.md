---
layout: post
title:  Cifrar con gpgtar (anteriormente llamado gpg-zip)
date:   2019-07-22 15:32:14 -0300
categories: Cifrado Debian
---

Para cifrar una carpeta y todo su contenido uso la herramienta **gpgtar** del paquete (gnupg-utils). Es muy sencilla y es una buena opción porque es muy resistente a los ataques.

Para cifrar con gpgtar se hace así:

`$ gpgtar -co carpeta_cifrada.gpg ./carpeta/`

Así obtengo un archivo `carpeta_cifrada.gpg` que empaqueta la carpeta completamente cifrada.

Para desencriptar la carpeta usamos el comando siguiente:

`$ gpgtar -d carpeta_cifrada.gpg`

Siempre he usado gpg-zip pero en Debian 10 me salta un mensaje de advertencia indicando que es mejor usar gpgtar.
Tras instalar Debian 10.3 o 10.4 me daba un mensaje de error algo así como:
>`gpg: signing failed: Inappropriate ioctl for device`

Mirando [aquí](https://github.com/keybase/keybase-issues/issues/2798) logré solucionarlo con: `export GPG_TTY=$(tty)`. Además me gusta más que antes porque la contraseña te la pide en la propia consola, antes me la pedía en una ventana gráfica y no me gustaba ese salto de la consola a una ventana gráfica.

[Fuente](http://www.taringa.net/posts/linux/18019134/Como-encriptar-carpetas-en-Linux-con-GPG.html)
___

También te puede interesar: [Carpeta Cifrada nativa Ext4](https://witopea.github.io/carpeta-cifrada-nativa-ext4/)