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

Para solventarlo hice un simple:
`export DISPLAY=:0
`

Y funcionó :).