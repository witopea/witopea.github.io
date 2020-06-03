---
layout: post
title:  Tips ffmpeg
date:   2020-04-23 18:12:40
categories: Debian
---
Iré añadiendo recetas de ffmpeg que voy necesitando para que no se me olviden.

## 1 Cortar vídeo (sin re-codificar)
`ffmpeg -i input.mp4 -ss 00:01:30 -to 00:02:00 -c copy output.mp4`
> Nos quedaríamos con el vídeo que va desde el minuto 1:30 al minuto 2:00

## 2 Quitar audio a un vídeo (sin re-codificar)
`ffmpeg -i input.mp4 -vcodec copy -an output.mp4`

## 3 Añadir audio a un vídeo (sin re-codificar)
`ffmpeg -i video_original.mp4 -i audio.mp4 -c copy video_con_audio.mp4`
> Normalmente el vídeo original no tiene audio porque se lo hemos quitado con el tip anterior.

## 4 Girar vídeo
FFMpeg has a feature called “Transpose” that is used to rotate videos. Using this feature, we can easily rotate videos clockwise and counter-clockwise as well as flip them vertically and horizontally.

For example, the following command will rotate the given video by 90 degrees clockwise:

`ffmpeg -i input.mp4 -vf "transpose=1" output.mp4`

[::Fuente::](https://www.ostechnix.com/how-to-rotate-videos-using-ffmpeg-from-commandline/)
