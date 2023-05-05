## Descripción
The flag is somewhere on this web application not necessarily on the website. Find it.Check [this](http://saturn.picoctf.net:61304/) out.

## Pistas 

## Solución
- Con el título del reto parecía insinuar que se trataba de la fuente "Roboto" o "Sans", las cuales se encuentran en los apartados de estilo de la página, sin embargo, después de mucho buscar no aparecía la bandera en ninguno de los archivos listados.
- Otra interpretación al título del reto puede ser que se trate del archivo robots.txt. Así que entramos a  http://saturn.picoctf.net:61304/robots.txt y obtenemos lo siguiente:
```
User-agent *
Disallow: /cgi-bin/
Think you have seen your flag or want to keep looking.

ZmxhZzEudHh0;anMvbXlmaW

svssshjweuiwl;oiho.bsvdaslejg
Disallow: /wp-admin/
```

- El texto del final parece necesitar que lo decodifiquemos, así que con ayuda de cyberchef nos damos cuenta se trata de texto en base64
- Ahora tenemos dos rutas diferentes :
	- flag1.txtjs/myfi
	- js/myfile.txt
La segunda parece tener el mejor formato, así que ahora ingresamos a http://saturn.picoctf.net:61304/js/myfile.txt.
- Obtenemos la bandera
## Bandera
picoCTF{Who_D03sN7_L1k5_90B0T5_718c9043}

## Notas Adicionales
A robots.txt file tells search engine crawlers which URLs the crawler can access on your site. This is used mainly to avoid overloading your site with requests; **it is not a mechanism for keeping a web page out of Google**. To keep a web page out of Google, [block indexing with `noindex`](https://developers.google.com/search/docs/crawling-indexing/block-indexing) or password-protect the page.

## Referencias
https://developers.google.com/search/docs/crawling-indexing/robots/intro