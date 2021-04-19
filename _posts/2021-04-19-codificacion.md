---
layout: post
title:  Problemas codificación
date:   2021-04-19 10:10:32
categories: Debian
---
A veces cuando usas algún archivo de texto te das cuenta que no está bien codificado. Algunas veces esto sucede porque proceden de Windows. Me ha pasado muchas veces con archivos LaTeX.

Lo primero es instalar el paquete convmv en tu Debian:

`# apt install convmv`

Después de esto ejecuto en la carpeta donde se encuentran los archivos de texto lo siguiente:

`find /RUTA_DIRECTORIO/ -type f -exec convmv -f iso-8859-1 -t utf8  {} --notest \;`

Eso es todo :)