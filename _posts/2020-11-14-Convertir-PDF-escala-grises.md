---
layout: post
title:  Convertir PDF a escala de grises
date:   2020-11-14 20:12:40
categories: Debian, PDF
---
A veces tenemos archivos PDF muy pesados y queremos leerlos por ejemplo en un móvil. Para ello cuanto menos pese mucho mejor para su manejo. Podemos hacerlo de la siguiente forma:

`gs -sDEVICE=pdfwrite -dProcessColorModel=/DeviceGray -dColorConversionStrategy=/Gray -dPDFUseOldCMS=false -o output.pdf -f input.pdf`

[::Fuente::](https://stackoverrun.com/es/q/5497076)