---
layout: post
title:  Man Pages en español
date:   2019-07-30 15:33:14 -0300
categories: Debian
---

Mi sistema siempre lo tengo en inglés me gusta porque de esa forma me obligo a aprender este idioma sin
necesidad de estudiar.

Quería consultar una página del man en español pero no quería cambiar el idioma de instalación de mi equipo. 

Pues se puede hacer. Primero te aseguras de que están instalados los paquetes necesarios.

`# apt install manpages-es manpages-es-extra`

`$ export LC_MESSAGES=es`

Después para hacer la consulta por ejemplo del manual de **man** en español hago lo siguiente:

`man -L es man`

O también

`man --locale=es man`

Ojo hay muchos manuales que sólo están disponibles en inglés. Por ejemplo el manual de **su**
cuando he ido a consultarlo estaba sólo en inglés.

Y eso es todo.

[Fuente](http://curioseandolinux.blogspot.com/2011/03/instalacion-de-las-manpages-es-y-extras.html) 
