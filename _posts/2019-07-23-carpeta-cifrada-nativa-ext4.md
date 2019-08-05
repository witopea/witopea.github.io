---
layout: post
title:  Carpeta Cifrada nativa Ext4
date:   2019-07-23 15:32:14 -0300
categories: Cifrado Debian
---
## gpg-zip

Hasta el momento he usado la
herramienta **gpg-zip** del paquete (gnupg-utils) para cifrar
una carpeta y todo su contenido.
Es muy sencilla. Al parecer es una buena opción ya que la herramienta gnugpg es muy resistente a los ataques.

Para cifrar con gpg-zip se hace así:

`$ gpg-zip -c -o carpeta_cifrada.gpg ./carpeta`

Así obtengo un archivo `carpeta_cifrada.gpg` que empaqueta la carpeta completamente cifrada.

Para desencriptar la carpeta usamos el comando siguiente:

`$ gpg-zip -d carpeta_cifrada.gpg`

[Fuente](http://www.taringa.net/posts/linux/18019134/Como-encriptar-carpetas-en-Linux-con-GPG.html)

## Cifrado nativo Ext 4

Quería investigar otras opciones
y comento aquí una interesante que
desconocía.

El sistema de archivos Ext4 
implementa de forma nativa
la encriptación.

Para usar esta característica de
momento he seguido los siguientes pasos:

1. He creado un archivo de 20 Megas
`# dd if=/dev/zero of=unidad bs=1M count=20`

2. Lo formateo a Ext4 con blocksize 4096
`# mkfs -t ext4 -b 4096 unidad`

3. Activo su flag de encriptación:`# tune2fs -O encrypt unidad`
4. Comprobamos que los comandos `# tune2fs -l /dev/device | grep 'Block size'`y `# getconf PAGE_SIZE` nos devuelven Block Size igual a 4096.
5. Monto el archivo unidad en una carpeta dentro de /media/tu_usuario
`# mount -o loop /home/witopea/unidad /media/witopea/unidad/`

6. Creo la carpeta prueba en la que voy a meter el contenido a cifar,
(es importante que la carpeta que vayas a usar esté vacía).

7. Introduzco la contraseña con la que quiero cifrar
`$ /usr/sbin/e4crypt add_key`

8. Le asigno esa clave a la carpeta que he creado desde su carpeta madre (../)
`$ /usr/sbin/e4crypt set_policy key nombre_carpeta`

9. Tras eso puedes añadir a la carpeta vacía el contenido que quieras.

Después del `$ e4crypt add_key` esa key queda activa durante toda la sesión y puedes consultar el contenido de la carpeta descifrada.
Ahora estoy viendo como desactivar esa key para que la carpeta aparezca nuevamente cifrada sin tener que cerrar la sesión.

Gracias a `@hambaglio` y `@YukiteruAmano` del grupo de Telegram *Debian_es* y a la [wiki de Arch](https://wiki.archlinux.org/index.php/Ext4#Using_file-based_encryption)
