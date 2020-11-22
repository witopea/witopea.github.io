---
layout: post
title:  Congela tus repos
date:   2020-11-22 10:10:32
categories: Debian
---
Hacía tiempo que no instalaba Debian testing, lo acabo de hacer y va todo como la seda. Como no me quiero que el sistema se rompa he recordado una de las cosas que hacía hace muchos años que era congelar los repos.

Debian tiene publicados sus repos por fechas en la página [snapshot](https://snapshot.debian.org/) y puedes buscarlos por fechas para elegir la que quieras. Así tu sistema está actualizado a dicha fecha y si quieres instalar cosas las instalas de ahí evitando posibles roturas de tu sistema con alguna actualización.

En mi sources.list he puesto esto:

`deb [check-valid-until=no] https://snapshot.debian.org/archive/debian/20201122T094144Z/ bullseye main contrib non-free`

Saludos.