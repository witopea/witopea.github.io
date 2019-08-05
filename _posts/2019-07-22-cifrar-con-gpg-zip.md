---
layout: post
title:  Cifrar con gpg-zip
date:   2019-07-22 15:32:14 -0300
categories: Cifrado Debian
---

Para cifrar una carpeta y todo su contenido uso la herramienta **gpg-zip** del paquete (gnupg-utils). Es muy sencilla y es una buena opción porque es muy resistente a los ataques.

Para cifrar con gpg-zip se hace así:

`$ gpg-zip -c -o carpeta_cifrada.gpg ./carpeta`

Así obtengo un archivo `carpeta_cifrada.gpg` que empaqueta la carpeta completamente cifrada.

Para desencriptar la carpeta usamos el comando siguiente:

`$ gpg-zip -d carpeta_cifrada.gpg`

[Fuente](http://www.taringa.net/posts/linux/18019134/Como-encriptar-carpetas-en-Linux-con-GPG.html)
___
También te puede interesar: [Carpeta Cifrada nativa Ext4](https://witopea.github.io/Conectar-a-wifi-desde-el-terminal/)