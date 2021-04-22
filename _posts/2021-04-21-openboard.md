---
layout: post
title:  Openboard
date:   2021-04-19 10:10:32
categories: Debian
---
[Openboard](https://openboard.ch/download.en.html) es una fantástica aplicación de pizarra digital de software libre.
Su paquete de instalación se quedó en la versión Ubuntu 16.04 pero afortunadamente tenemos disponible una versión en appImage [aquí](https://github.com/miurahr/OpenBoard-AppImage/releases). Por cierto la versión snap no funciona al menos a fecha de la publicación de este artículo.

El botón de **Show Desktop** me ha dado algún problema de transparencias con el escritorio, afortunadamente [aquí](https://github.com/OpenBoard-org/OpenBoard/issues/66) abajo del todo en el comentario del 4 de diciembre de 2019 encontré la solución. Hay que tener un compositor de pantallas en funcionamiento como por ejemplo xcompmgr.
Si ejecutas ese comando antes de abrir openboard funciona sin problemas la transparencia.

Eso es todo :)