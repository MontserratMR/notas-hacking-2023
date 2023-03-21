## Descripción
Find the flag being held on this server to get ahead of the competition http://mercury.picoctf.net:45028/

## Pistas 
1. Maybe you have more than 2 choices
2. Check out tools like Burpsuite to modify your requests and look at the responses
## Solución
Vemos el archivo html sale algo como esto:

```
<div class="col-md-6">
                    <div class="panel panel-primary" style="margin-top:50px">
                        <div class="panel-heading">
                            <h3 class="panel-title" style="color:red">Red</h3>
                        </div>
                        <div class="panel-body">
                            <form action="index.php" method="GET">
                                <input type="submit" value="Choose Red"/>
                            </form>
                        </div>
                    </div>
                </div>
                <div class="col-md-6">
                    <div class="panel panel-primary" style="margin-top:50px">
                        <div class="panel-heading">
                            <h3 class="panel-title" style="color:blue">Blue</h3>
                        </div>
                        <div class="panel-body">
                            <form action="index.php" method="POST">
                                <input type="submit" value="Choose Blue"/>
                            </form>
                        </div>
                    </div>
                </div>
```
Podemos ver que se utilizan dos métodos diferentes. "GET" y "POST", por lo que la sugerencia probablemente se refiera a un tercer método y podemos ver que aparece "HEAD" en el título. Probemos una solicitud "HEAD".
```
curl -I HEAD -i http://mercury.picoctf.net:53554/index.php
```
Y nos regresa la bandera

## Bandera
picoCTF{r3j3ct_th3_du4l1ty_775f2530}

## Notas Adicionales
HTTP request methods

GET
The GET method requests a representation of the specified resource. Requests using GET should only retrieve data.

HEAD
The HEAD method asks for a response identical to a GET request, but without the response body.

POST
The POST method submits an entity to the specified resource, often causing a change in state or side effects on the server.

## Referencias
https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods