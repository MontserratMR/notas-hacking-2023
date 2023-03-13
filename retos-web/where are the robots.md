## Descripción
Can you find the robots? https://jupiter.challenges.picoctf.org/problem/36474/

## Pistas 
What part of the website could tell you where the creator doesn't want you to look?

## Solución
Al momento de acceder al  https://jupiter.challenges.picoctf.org/problem/36474/robots.txt nos mostrará el archivo con:
```
User-agent: *
Disallow: /477ce.html
```
lo que quiere decir que está bloqueando el acceso al archivo html 477ce
Accedemos a este con  https://jupiter.challenges.picoctf.org/problem/36474/477ce.html y nos tenemos la bandera.

## Bandera
picoCTF{ca1cu1at1ng_Mach1n3s_477ce}

## Notas Adicionales
What is a robots.txt file?
Robots.txt is a text file webmasters create to instruct web robots (typically search engine robots) how to crawl pages on their website. The robots.txt file is part of the the robots exclusion protocol (REP), a group of web standards that regulate how robots crawl the web, access and index content, and serve that content up to users. The REP also includes directives like meta robots, as well as page-, subdirectory-, or site-wide instructions for how search engines should treat links (such as “follow” or “nofollow”).

In practice, robots.txt files indicate whether certain user agents (web-crawling software) can or cannot crawl parts of a website. These crawl instructions are specified by “disallowing” or “allowing” the behavior of certain (or all) user agents.

## Referencias
https://moz.com/learn/seo/robotstxt