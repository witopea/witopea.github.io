---
layout: post
title:  Errores al iniciar
date:   2020-11-08 10:42:36
categories: Debian
---
A veces cuando hacemos una instalación en Debian o similares, nos aparecen mensajes de error al iniciar. Tras investigar el posible error, muchas veces concluimos que el error es irrelevante pero no conseguimos hacerlo desaparecer (ACPI Error, o similares...)

[Aquí](https://exdebian.org/foro/netbook-samsung-n150-error-acpi-durante-el-inicio) dan una solución para que deje de aparecer.

`# nano /etc/default/grub`

Añadimos **loglevel=3**, queda algo como esto:

`GRUB_CMDLINE_LINUX_DEFAULT="quiet loglevel=3"`

Y adiós error, al menos a mí me ha funcionado :).