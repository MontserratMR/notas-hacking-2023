## Descripción
There is some interesting information hidden around this site [http://mercury.picoctf.net:5080/](http://mercury.picoctf.net:5080/). Can you find it?

## Pistas 
You should have enough hints to find the files, don't run a brute forcer. 
## Solución
Después de leer la descripción, parece que la bandera está escondida en algún lugar y tenemos que ir a una búsqueda del tesoro.
* Al checar el archivo html encontramos la primera parte de la bandera
* La segunda parte de la bandera se encuentra en el archivo css
* Cuando entramos al archivo JavaScript no hay bandera, pero nos da una pista que nos sugiere buscar en el robots.txt ("How can I keep Google from indexing my website?"). Ahí encontramos la tercera parte. 
* La siguiente pista que nos deja el último archivo es "I think this is an apache sever... can you Access the next flag?", lo cual nos indica que tenemos que entrar al archivo .htaccess, donde encontramos la cuarta parte de la bandera.
* La última pista que nos da es "I love making websites on my Mac, I can Store a lot of information there", lo cual nos indica que tenemos que entrar al archivo .DS_Store, ahí encontramos la última parte de la bandera.


## Bandera
picoCTF{th4ts_4_l0t_0f_pl4c3s_2_lO0k_35844447}
## Notas Adicionales
robots.txt: Un archivo robots.txt le dice a los rastreadores de los motores de búsqueda a qué URL puede acceder el rastreador en su sitio. Esto se usa principalmente para evitar sobrecargar su sitio con solicitudes.

.htaccess: es un poderoso archivo de sitio web que controla la configuración de alto nivel de su sitio web. En servidores que ejecutan Apache (un software de servidor web), el . htaccess le permite realizar cambios en la configuración de su sitio web sin tener que editar los archivos de configuración del servidor.

.DS_Store: El . El archivo DS_Store, que significa Desktop Services Store, es un archivo invisible que se crea automáticamente cada vez que abre una carpeta con Finder en macOS. Este archivo seguirá a la carpeta dondequiera que vaya, incluso cuando esté comprimido en un archivo ZIP.

## Referencias
https://developers.google.com/search/docs/crawling-indexing/robots/intro#:~:text=A%20robots.txt%20file%20tells,web%20page%20out%20of%20Google.

https://ithemes.com/blog/what-is-the-htaccess-file/#:~:text=htaccess%20file%20is%20a%20powerful,to%20edit%20server%20configuration%20files.

https://techjd.medium.com/so-what-is-that-ds-store-file-anyway-2255022d0d83?source=user_profile---------3----------------------------#:~:text=The%20.,compressed%20in%20a%20ZIP%20file.
