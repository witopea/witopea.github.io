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
`ffmpeg -i input.mp4 -i audio.mp4 -c copy output.mp4`
> Normalmente el vídeo original no tiene audio porque se lo hemos quitado con el tip anterior.


## Unir vídeos
`cat input1.mp4 input2.mp4 input3.mp4 > output.mp4`
> Sencillísimo comando. Con fmpeg también se puede pero lo veo más complicado.

## 5 Girar vídeo
FFMpeg has a feature called “Transpose” that is used to rotate videos. Using this feature, we can easily rotate videos clockwise and counter-clockwise as well as flip them vertically and horizontally.

For example, the following command will rotate the given video by 90 degrees clockwise:

`ffmpeg -i input.mp4 -vf "transpose=1" output.mp4`

[::Fuente::](https://www.ostechnix.com/how-to-rotate-videos-using-ffmpeg-from-commandline/)

## 6 Subir sonido
Así he subido el volumen de un vídeo:

`ffmpeg -i input.mkv -vcodec copy -af "volume=1.5" output.mkv`

## 7 Extraer audio (sin recodificar)
Primero podemos ver las características del audio contenido en nuestro vídeo.

`ffprobe input.mp4`

Después hacemos esto `ffmpeg -i input.mp4 -vn -acodec copy output.m4a`

[::Fuente::](https://www.linuxuprising.com/2019/11/ffmpeg-extract-audio-from-video-in.html)

## 8 Convertir a ogg

`ffmpeg -i input.mp4 -acodec libvorbis -aq 4 -vn -ac 2 -map_metadata 0 output.ogg`

[::Fuente::](https://iaroki.github.io/blog/convert-m4a-to-ogg-with-ffmpeg/)

## 9 Convertir a mp3

`ffmpeg -i input.mp4 -codec:a libmp3lame -aq 4 -vn -ac 2 -map_metadata 0 output.mp3`

## 10 Imagen + audio
`ffmpeg -i imagen_input.jpg -i audio_input.m4a -tune stillimage -c:a copy output.mp4`
[::Fuente::](https://superuser.com/questions/1041816/combine-one-image-one-audio-file-to-make-one-video-using-ffmpeg)
