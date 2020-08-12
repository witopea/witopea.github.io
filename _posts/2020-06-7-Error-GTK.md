---
layout: post
title:  Gtk-WARNING - Abrir aplicaciones GUI como root
date:   2020-06-07 18:12:40
categories: Debian
---
Obtuve el error:

`(gpartedbin:6806): Gtk-WARNING **: 21:35:28.909: cannot open display: :0.0
`

Este error salió después de intentar abrir gparted con privilegios root.

En algunos sitios vi que haciendo un `export DISPLAY=:0` se solucionaba y me llegó a funcionar pero dejó de funcionar no sé muy bien por que.


[Aquí](https://laguialinux.es/gtk-warning-cannot-open-display-0/) di con la solución.

Hay que hacer un `$ xhost +` y después ya funciona sin problema.
Para que esto sea permanente recomiendan agregarlo al .bashrc de tu usuario.

`echo ‘xhost + && clear’ >> $HOME/.bashrc`
