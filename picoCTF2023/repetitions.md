## Descripción
Can you make sense of this file? Download the file [here](https://artifacts.picoctf.net/c/294/enc_flag).

## Pistas 
Multiple decoding is always good.

## Solución
El archivo nos muestra un texto en Base64. Si lo decodificamos seis veces llegamos a la bandera.

## Bandera
picoCTF{base64_n3st3d_dic0d!n8_d0wnl04d3d_1bfa7005}

## Notas Adicionales
Una forma de conseguirlo es usando una herramienta como CyberChef

## Referencias
https://gchq.github.io/CyberChef/#recipe=From_Base64('A-Za-z0-9%2B/%3D',true,false)&input=Y0dsamIwTlVSbnRpWVhObE5qUmZiak56ZEROa1gyUnBZekJrSVc0NFgyUXdkMjVzTURSa00yUmZNV0ptWVRjd01EVjlDZz09Cgo