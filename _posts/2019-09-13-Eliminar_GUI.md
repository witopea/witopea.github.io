---
layout: post
title:  Eliminar entorno gráfico y aplicaciones gráficas
date:   2019-09-13 01:42:14 -0300
categories: Debian
---
`apt purge --auto-remove 'libx11-.*'`

Siempre he buscado la forma de eliminar todo el entorno gráfico de mi instalación. A veces quieres empezar de nuevo con una instalación limpia y este comando que pongo a continuación te elimina el entorno gráfico y todas las aplicaciones gráficas, o al menos eso es lo que creo. Aún no lo he probado pero tiene que dejar el sistema muy limpio para volver a empezar si no quieres volver a instalar desde cero. Yo tengo mi script de instalación en el que instalo las aplicaciones que necesito para mi openbox y el sistema quedaría listo en poco tiempo.
