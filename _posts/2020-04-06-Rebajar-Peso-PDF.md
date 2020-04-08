---
layout: post
title:  Rebajar peso a un PDF
date:   2020-04-06 22:12:40
categories: Debian
---
A veces tenemos archivos PDF muy pesados y queremos leerlos por ejemplo en un móvil. Para ello cuanto menos pese mucho mejor para su manejo. Podemos hacerlo de la siguiente forma:

`gs -sDEVICE=pdfwrite -dCompatibilityLevel=1.4 -dPDFSETTINGS=/ebook -dNOPAUSE -dQUIET -dBATCH -sOutputFile=output.pdf input.pdf`

Estas son algunas de las opciones:

- **dPDFSETTINGS=/screen** lower quality, smaller size. (72 dpi)
- **dPDFSETTINGS=/ebook** for better quality, but slightly larger pdfs. (150 dpi)
- **dPDFSETTINGS=/prepress** output similar to Acrobat Distiller "Prepress Optimized" setting (300 dpi)
- **dPDFSETTINGS=/printer** selects output similar to the Acrobat Distiller "Print Optimized" setting (300 dpi)
- **dPDFSETTINGS=/default** selects output intended to be useful across a wide variety of uses, possibly at the expense of a larger output file

La opción que suelo usar es **ebook**.

Bye :)