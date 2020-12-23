---
layout: post
title:  Instalar app snap
date:   2020-12-23 10:10:32
categories: Debian
---
No me gusta mucho snap, de hecho lo he evitado a lo largo del tiempo, pero hoy me he visto en la necesidad de usarlo. Tengo que instalar la aplicación exeLearning y con Debian Testing(BullSeye) no me funciona. Como está disponible para snap la he instalado desde ahí.

Lo primero es instalar snap en tu Debian:

`# apt install snapd`
`# snap install core`

Después instalamos la aplicación desde snap:

`# snap install exelearning`

Y posteriormente para ejecutarla

`$ snap run exelearning`

Eso es todo :)