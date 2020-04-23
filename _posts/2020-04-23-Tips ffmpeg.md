---
layout: post
title:  Tips ffmpeg
date:   2020-04-23 18:12:40
categories: Debian
---
Iré añadiendo recetas de ffmpeg que voy necesitando para que no se me olviden.

## 1 Cortar vídeo sin re-codificarlo
`ffmpeg -ss 00:01:30 -to 00:02:00 -c copy -i video.mp4 nombre_final.mp4`
> Nos quedaríamos con el vídeo que va desde el minuto 1:30 al minuto 2:00
> -i es el vídeo original