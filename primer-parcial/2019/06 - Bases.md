## Descripción
What does this `bDNhcm5fdGgzX3IwcDM1` mean? I think it has something to do with bases.

## Pistas 
Submit your answer in our flag format. For example, if your answer was 'hello', you would submit 'picoCTF{hello}' as the flag.

## Solución
La pista nos dice que tiene algo que ver con bases. En retos anteriores conocimos la Base64, un grupo de esquemas de codificación de binario a texto en formato de cadena ASCII traduciéndolos a una representación rádix-64. 
Existen varias formas de abordar el problema, en mi caso utilicé la herramienta "CyberChef": ingresé `bDNhcm5fdGgzX3IwcDM1` y me regresó la bandera.

## Bandera
picoCTF{l3arn_th3_r0p35}

## Referencias
https://gchq.github.io/CyberChef/#recipe=From_Base64('A-Za-z0-9%2B/%3D',true,false)&input=YkROaGNtNWZkR2d6WDNJd2NETTE